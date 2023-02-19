# ingress暴露的服务中出现413报错

增加注解

```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  annotations:
    # 指定20m
    nginx.ingress.kubernetes.io/proxy-body-size: 20m
```

验证

```
kubectl exec -it nginx-ingress-controller-6b7f7f66-lpkkt grep 'client_max_body_size' nginx.conf -n ingress-nginx|grep 20m
```


### 保留自定义
```
apiVersion: v1
data:
  enable-underscores-in-headers: "true"
```