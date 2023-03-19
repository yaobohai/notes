## 华为云K8S集群产生大量的Evicted pod

1、查看具有evicted的pod的事件

```
for pod_name in $(kubectl get po -n production|grep 'Evicted'|awk '{print $1}');do echo -e "${pod_name}: $(kubectl describe pod -n production ${pod_name}|grep -Ew 'Node|
Message'|grep -v 'Node-Selectors')";done
```