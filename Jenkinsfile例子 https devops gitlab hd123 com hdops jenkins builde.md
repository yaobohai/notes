
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


这就说明jenkinsfile已经放在git仓库里了，接下来就是jenkins job在用这个文件的时候去git里拿；在jenkins上新建一个流水线job
