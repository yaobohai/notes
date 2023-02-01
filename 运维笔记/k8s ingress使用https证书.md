# [k8s] ingress使用https证书

## 创建secret

```bash
$ kubectl create secret tls 证书名 --key STAR_itan90_cn.key --cert STAR_itan90_cn.crt -n 命名空间
```

## 查看secret

```bash
$ kubectl describe secret 证书名 -n ops
```

## 配置ingress

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: demo
  annotations:
    kubernetes.io/ingress.class: "nginx"
spec:
  rules:
  - host: 域名
  ......
  tls:
    - hosts:
        - 域名
      secretName: 证书名
```


