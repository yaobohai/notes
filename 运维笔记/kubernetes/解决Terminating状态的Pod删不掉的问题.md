# 解决Terminating状态的Pod删不掉的问题

偶现部分pod（实例）一直处于“Terminating ”状态：

```
$ kubectl get pod -A | grep Terminating
int             gateway-service-5b8874dd7b-q4wn8                        3/3     Terminating   0               21d
int             ras-service-8658b48f5-756zg                             3/3     Terminating   0               21d
int             sas-service-89a8h81-9765d746f-jf2pk                     3/3     Terminating   0               21d
```

解决方法:

```
$ kubectl delete pods -n <namespace> <podname> --grace-period=0 --force
```