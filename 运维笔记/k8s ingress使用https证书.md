# [k8s] ingress使用https证书

## 创建secret

```bash
$ kubectl create secret tls 证书名 --key key文件 --cert crt文件 -n 命名空间
```

或使用yaml方式创建

```
apiVersion: v1
kind: Secret
metadata:
  name: testsecret-tls
  namespace: 命名空间
data:
  tls.crt: base64 encoded cert
  tls.key: base64 encoded key
type: kubernetes.io/tls
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


