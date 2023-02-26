## 通过colab零成本生成 AI 照片 -- ChilloutMix & Lora


先看下效果：

![使用 Stable Diffusion 生成的照片](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/WjDPGO.jpg)



准备材料：

- 谷歌账号
- 富强代理 (懂得都懂吧？)
- 运算资源 https://colab.research.google.com/ 
- 存放模型的硬盘 https://drive.google.com/ 
- 模型&关键词 https://civitai.com/


## 1.下载 LORA 模型到本地

```
打开链接下载模型，也可以打开 civitai.com 下载其他模型
https://civitai.com/models/7448/korean-doll-likeness
https://civitai.com/models/7716/taiwan-doll-likeness
https://civitai.com/models/10135/japanese-doll-likeness
```


![点箭头位置](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/PKHuAX.jpg)

## 2.将模型上传到 Google 云端硬盘

```
1、在浏览器打开链接：https://drive.google.com/
2、新建一个 " model " 的目录,用来存储模型
```

![新建模型目录](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/vUuw7A.png)


![将下载的模型上传](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/igfEIX.jpg)

## 3.在 Colab 运行

```
在浏览器打开链接：

https://colab.research.google.com/drive/1FFGO7zyrZwp0yePWdK1cH_s-75wx6JOF?usp=share_link
```

### 3.1 初始化

打开后，点击 “连接” 或 “连接到托管的运行时”

![连接](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/5saVpI.png)

当出现 2 时的绿色打勾以及可观察到资源使用时表示已经连接到可分配到计算资源

![初始化](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/s0EXBi.png)

稍等片刻，初始化操作略慢，初始化整个资源库8、9G大小这样，当底部出现 “Runing” 的时候 再次点击运行的图标，停止运行。

![停止运行](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/e1xldA.png)

### 3.2 挂载云盘

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/gZChT3.png)

### 3.3 复制模型

挂载云盘完成后，就可以把 当时上传到 “model” 目录下的模型文件复制到工作目录了，如果在第 2 步骤中，新建的目录名不叫 model ，那自行修改下即可

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/abOunF.png)

### 3.4 运行stable-diffusion

点击运行运行旁边的启动按钮，则可在colab运算资源中运行stable-diffusion运算项目，当出现 `Running on public URL` 则说明项目启动完毕，接着点击该链接，会跳转到一个新的页面：“stable-diffusion-webui” 此时colab的页面我们不用去管他 (也不要关闭)。

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/urkl4u.png)


## 4. 制作图形

### 4.1 导入模型

点橙色按钮 `Generate` 下面的第三个按钮，接着来到Lora层级，选择三个任意一个模型。

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/NVGsNZ.jpg)

### 4.2 配置参数

在 4.1 选择好模型后，会自动在上方第一个大框中填上模型的前缀，然后我们在后面加上一些我们想要的参数

![](https://resource.static.tencent.itan90.cn/mac_pic/2023-02-26/POdms6.png)

第一个框中输入的参数：

```
// 注意事项：选一个模型之后，会自动在第一个输入框填充前缀，不要删除

1 girl in JK uniform,cute,wear glasses,solo,stand,dating,(nose blush),(smile:1.15),(grin) big breasts,Long legged
```



