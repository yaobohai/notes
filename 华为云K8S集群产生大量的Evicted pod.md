## 华为云K8S集群产生大量的Evicted pod

1、查看具有evicted的pod的事件

```
for pod_name in $(kubectl get po -n production|grep 'Evicted'|awk '{print $1}');do echo -e "${pod_name}: \n $(kubectl describe pod -n production ${pod_name}|grep -Ew 'Node|Message'|grep -v 'Node-Selectors')";echo '' ;done
```


2、报错原因

```
nightfury-service-6fd4347-65f4b974c5-bz6mz:
 Node:           172.30.218.222/
Message:        Pod The node had condition: [DiskPressure].
```


3、根据报错提示，说明节点磁盘可能存在瓶颈，登录到指定的节点，通过 `df -hT` 查看磁盘使用情况

```

```