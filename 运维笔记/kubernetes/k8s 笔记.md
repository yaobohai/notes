# k8s 笔记

 ## 常用工具下载

```shell
# argocd
wget https://init.ac/files/argocd -P /usr/local/bin/ && chmod +x /usr/local/bin/argocd

# kustomize
wget https://init.ac/files/kustomize -P /usr/local/bin/ && chmod +x /usr/local/bin/kustomize

# kubectl-node_shell
wget https://init.ac/files/kubectl-node_shell -P /usr/local/bin/ && chmod +x /usr/local/bin/kubectl-node_shell
```

## 复制k8s容器内的文件

```shell
kubectl cp <命名空间>/<pod-name>:<容器文件路径> <主机路径>
```

## 登录k8s节点

```
wget https://init.ac/files/kubectl-node_shell -P /usr/local/bin/ && chmod +x /usr/local/bin/kubectl-node_shell

kubectl get node
kubectl node-shell <node-name>
```

## 问题排查工具


### dnsutils

- 支持ping、nslookup等常用网络层面需要的命令

```
apiVersion: v1
kind: Pod
metadata:
  name: dnsutils
spec:
  containers:
  - name: dnsutils
    image: mydlqclub/dnsutils:1.3
    imagePullPolicy: IfNotPresent
    command: ["sleep","3600"]
```

