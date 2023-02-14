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
``