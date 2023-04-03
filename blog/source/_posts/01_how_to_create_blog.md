---
title: 如何使用Vercel部署自己的Blog
date: 2023-04-03 20:04:14
tags: vercel;Blog;Deploy 
---

# 如何使用Vercel部署自己的Blog

从CZY那儿得到启发，遂想建立属于自己的Blog，用于记录自己的科研+工作的过程

从零开始用`vue+springboot` 搭建一个博客的话，固然自由度高，但是搭建过程有些许慢

想想，还是直接使用既有的博客框架吧！



> 部署平台：Vercel
>
> 代码托管：Github
>
> 博客框架：Hexo



## 简单几步搞定自己的Blog

Step1： 注册一个[Vercel](https://vercel.com)的账户，我使用的是GitHub账户来注册的，方便后续项目托管

![image-20230403172934273](image-20230403172934273.png)

Step2：注册完成后，点击右上角 **头像**  进入你的  **Dashboard **当中，管理面板中可以看到你目前的项目；点击中下方的 **Create a New Project** 或者点击右上方的 **Add New** 来创建一个新的 Project

![image-20230403174419623](image-20230403174419623.png)



Step3：进入模板创建页面，两个方式：（1）通过github导入模板项目；（2）在Template市场寻找模板；这里我用的是第一种，那就是现在github上搜索 hexo 模板，在本地搭建部署好后，再import到vercel来

![image-20230403173320349](image-20230403173320349.png)

Step4: 填写项目配置，然后点击 Deploy 进行部署，等待片刻;

注意两个事情：

Project Name：不能加入大写，只能够小写

Root Directory：需要修改成对应的blog目录

![image-20230403174607962](image-20230403174607962.png)

![image-20230403175340300](image-20230403175340300.png)

Step5：可以在github上找找自己喜欢的主题，然后导入到项目中去，我目前找的是 **Fluid** 这个主题，还挺好看

**推荐几款美观的主题：**

[8 款颜值爆赞的 Hexo 主题推荐！快来搭建个人博客玩玩 | Github掘金计划 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/491537945)



最终的成品如下：

![image-20230403173631051](image-20230403173631051.png)

