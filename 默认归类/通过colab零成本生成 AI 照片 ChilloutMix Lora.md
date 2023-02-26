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




