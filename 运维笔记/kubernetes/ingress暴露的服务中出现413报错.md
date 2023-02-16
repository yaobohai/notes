# ingress暴露的服务中出现413报错

```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  annotations:
    kubernetes.io/ingress.class: ingress-nginx
    kubernetes.io/ingress.rule-mix: "true"
    kubernetes.io/ingress.subnetId: subnet-p6o2dfv2
    nginx.ingress.kubernetes.io/proxy-body-size: 20m
```