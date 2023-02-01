# [k8s] 容器启动前执行chmod授权操作

使用initContainers来完成

```yaml
      initContainers:
      - name: reset-permissions
        image: busybox:1.28
        securityContext:
          privileged: true
        command: ['sh', '-c', 'chmod 777 /bitnami/kafka']
```