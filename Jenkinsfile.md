
## Jenkinsfile

Jenkinsfile例子：https://devops-gitlab.hd123.com/hdops/jenkins_builder/-/blob/bohai/jenkinsfile/Jenkinsfile.bohai

Jenkinsfile内容：

```
def text="hello,world"
if (env.text){
    text =env.text
}

echo text
```

意思为：里面定义了一个变量text。默认值是hello,world；也可以读取JOB中环境变量env.text的值。加了个if判断如果env里面text不为空就拿env里面的值来echo输出；这个环境变量我们可以通过Jenkins的String Parameter来传入。

这个jenkinsfile在 https://devops-gitlab.hd123.com/hdops/jenkins_builder这个git工程下的`bohai`分支`jenkinsfile`目录里，文件名是`Jenkinsfile.bohai`

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-04-13/HMNhba.png)

Job中新增加String参数：勾选 `This project is parameterized` 并选择String Parameter

Name则是Jenkinsfile中的变量名`text` ，默认值可为空

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-04-13/yiMkGs.png)

之后划到最下方，在Pipline出，将 `Definition` 更换为 `Pipeline script from SCM` 从远程工程中拉取Pipline


