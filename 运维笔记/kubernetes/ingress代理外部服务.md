# ingress代理外部服务

## 创建service

```yaml
apiVersion: v1
kind: Service
metadata:
  name: kibana
  namespace: ops
spec:
  type: ClusterIP
  ports:
  - name: kibana
    port: 80
    protocol: TCP
    targetPort: 80
```

## 创建endpoint

```yaml
apiVersion: v1
kind: Endpoints
metadata:
  name: kibana
  namespace: ops
subsets:
- addresses:
  - ip: 10.0.0.12
  - ip: 10.0.0.13
  ports:
  - name: kibana
    port: 5601
    protocol: TCP
```

## 创建Ingress

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  annotations:
    kubernetes.io/ingress.class: "nginx"
  name: kibana
  namespace: ops
spec:
  rules:
    - host: kibana.bohai.com
      http:
        paths:
          - backend:
              service:
                name: kibana
                port:
                  number: 80
            path: /
            pathType: ImplementationSpecific
 # 开启ssl
  tls:
    - hosts:
        - kibana.bohai.com
      secretName: bohai
```