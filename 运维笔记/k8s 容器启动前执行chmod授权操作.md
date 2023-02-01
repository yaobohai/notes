# [k8s] 容器启动前执行chmod授权操作

步骤：挂载需要重新授权的存储，使用busybox来完成，具体yaml如下

```yaml
      initContainers:
      - name: reset-permissions
        image: busybox:1.28
        securityContext:
          privileged: true
        command: ['sh', '-c', 'chmod 777 /bitnami/kafka']
        volumeMounts:
        - name: kafka-storage-data
          mountPath: /bitnami/kafka
```