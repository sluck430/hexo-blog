---
title: hexo图片加载失败解决方案
date: 2023-04-03 21:29:55
tags: hexo;image;
---

# 一、先说如何让hexo图片成功显示出来

**Step1: 修改config设置** 

将_config.yml 设置文件中的 **post_asset_folder** 修改为 true

![img](image_1.png)

这一步的作用——在于之后每次使用`hexo new <title>`初始化新的博客文档时，就会在 source/_post/ 下生成一个与<title>.md文件同名的资源文件夹。

例如，输入`hexo new 01_how_to_create_blog`，就会出现以下结果，一个01_how_to_create_blog.md文档以及一个01_how_to_create_blog文件夹

![img](image_2.png)



**Step2: 安装插件**

通过以下npm命令安装 **hexo-asset-image** 插件

```plain
npm install https://github.com/CodeFalling/hexo-asset-image
```





**Step3：图片转移以及路径跟换**

将图片文件复制到同名文件夹中，并设置图片为相对路径；如下图所示，“01_how_to_create_blog/"文件夹下，图片已经从typora的图片缓存文件夹复制过来了，然后修改01_how_to_create_blog.md文件里的所有image路径，只留下图片名称。

![img](image_3.png)

![img](image_4.png)



**Step4：运行查看**

```plain
hexo generate
hexo server 
```



# 二、再说为什么会出现以下 /.com// 情况



目前看来，该错误其实是 **hexo-asset-image** 插件的bug



解决方法如下：

**Step1: 先卸载 hexo-asset-image**

```plain
npm uninstall hexo-asset-image
```

**Step2：重新下载正确的** **hexo-asset-image 插件**

```plain
npm install https://github.com/CodeFalling/hexo-asset-image
```

**Step3：运行三步走**

```plain
hexo clean
hexo generate
hexo server 
```



完成！

![img](image_5.png)





**参考博客：**

https://blog.csdn.net/ayuayue/article/details/109198493

https://segmentfault.com/q/1010000020310187