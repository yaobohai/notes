## 华为云K8S集群产生大量的Evicted pod

1、查看具有evicted的pod的事件

```
for pod_name in $(kubectl get po -n production|grep 'Evicted'|awk '{print $1}');do echo -e "${pod_name}: \n $(kubectl describe pod -n production ${pod_name}|grep -Ew 'Node|Message'|grep -v 'Node-Selectors')";echo '' ;done
```


2、错误原因

```
nightfury-service-6fd4347-65f4b974c5-bz6mz:
 Node:           172.30.218.222/
Message:        Pod The node had condition: [DiskPressure].
```


3、根据错误提示，说明节点磁盘可能存在瓶颈，登录到指定的节点，通过 `df -hT` 查看磁盘使用情况

```
[root@lianhuan-prd-hd-nodepool-new-w8mte-orm9v /]# df -hT
Filesystem                         Type      Size  Used Avail Use% Mounted on
devtmpfs                           devtmpfs  122G     0  122G   0% /dev
tmpfs                              tmpfs     123G     0  123G   0% /dev/shm
tmpfs                              tmpfs     123G  132M  122G   1% /run
tmpfs                              tmpfs     123G     0  123G   0% /sys/fs/cgroup
/dev/sda1                          ext4       49G  3.6G   43G   8% /
tmpfs                              tmpfs     123G   36K  123G   1% /tmp
/dev/mapper/vgpaas-dockersys       ext4      442G   27G  393G   7% /var/lib/containerd
/dev/mapper/vgpaas-kubernetes      ext4       49G   41G  6.0G  88% /mnt/paas/kubernetes/kubelet
```

可以看到，文件系统 `/dev/mapper/vgpaas-kubernetes`  磁盘使用率超过了80%,在k8s中，使用率超过85%则会驱逐节点中的pod到其他节点