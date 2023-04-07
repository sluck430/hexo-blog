---
title: 如何使用Vercel部署自己的Blog
date: 2023-04-03 20:04:14
tags: vercel;Blog;Deploy 
---

# 如何使用Vercel部署自己的Blog

本篇用于记录如何创建并部署自己的Blog



## 01 新的启航！New Start!

从 [CZY的博客](https://tech.jasonczc.cn/2022/guide/guide-use-vercel-and-hexo-to-build-freeblog/) 那儿得到启发，遂也想建立起属于自己的博客（Blog）

用于记录自己读研三年时光的 **科研过程 + 工作准备**，兴许还会有 **个人感悟** 

如果从零开始用 `Vue.js + Springboot + Mysql`  搭建一个前后端Blog，固然很值得练手且自由度相当高，但搭建成本还是挺大的，过程比较繁琐。

于是，经过缜密的思索，还是直接使用既有的博客框架吧！



以下是创建本Blog使用的 **技术栈** ：

- 部署托管： Vercel

- 博客框架： Hexo

- I     D    E： Vscode

- 代码仓库： Github



## 02 简单几步搞定自己的Blog

**Step1：** 注册一个 [Vercel（点我进入官网）](https://vercel.com) 的账户，我使用的是GitHub账户来注册的，方便后续项目托管

![image-20230403172934273](image-20230403172934273.png)

**Step2：**注册完成后，点击右上角 **头像**  进入你的  **Dashboard** 当中，管理面板中可以看到你目前的项目；点击中下方的 **Create a New Project** 或者点击右上方的 **Add New** 来创建一个新的 Project

![image-20230403174419623](image-20230403174419623.png)



**Step3：**进入模板创建页面，两个方式：（1）通过github导入模板项目；（2）在Template市场寻找模板；这里我用的是第一种，那就是现在github上搜索 hexo 模板，在本地搭建部署好后，再import到vercel来

![image-20230403173320349](image-20230403173320349.png)

**Step4:**  填写项目配置，然后点击 Deploy 进行部署，等待片刻;

注意两个事情：

Project Name：不能加入大写，只能够小写

Root Directory：需要修改成对应的blog目录

![image-20230403174607962](image-20230403174607962.png)

![image-20230403175340300](image-20230403175340300.png)

**Step5：**可以在github上找找自己喜欢的主题，然后导入到项目中去，我目前找的是 **Fluid** 这个主题，还挺好看

**推荐几款美观的主题：**

[8 款颜值爆赞的 Hexo 主题推荐！快来搭建个人博客玩玩 | Github掘金计划 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/491537945)



最终部署好的成品如下：

![image-20230403173631051](image-20230403173631051.png)



## 03 如何配置域名

部署项目后，Vercel会自动分配一个域名，同时它也支持用户配置自己的域名

Vercel分配的域名有时候从大陆方面访问不上，但是自己购买的域名就可以

感觉还是得自己整一个妥当



**Step1 : 购买域名**

首先得有一个属于自己的域名，可以到 [万网（阿里云）](https://wanwang.aliyun.com/?utm_content=se_1008775275)或者 [NameSilo](https://www.namesilo.com/) 上去购买

我这里是从 NameSilo 上买的 .top域名 sluckblog.top



**Step2: 增加记录**

回到Vercel，到Project -> Settings -> Domains 处，**Add** 新购买的域名

![image-20230404102514027](image-20230404102514027.png)

Add弹出框中，选择第三个即可，仅添加一个记录

![image-20230404102603508](image-20230404102603508.png)



**Step3： 域名解析**

上一步Add成功后，会出现以下情况，此时我们记住并复制 **Value** 值

![image-20230404102747495](image-20230404102747495.png)

回到购买域名网站的域名管理器页面

如果**Value** 值是IP，就添加一条A记录；

如果**Value** 值是地址，就添加一条CNAME记录；

![image-20230404103158380](image-20230404103158380.png)

添加解析成功后，回到Vercel，耐心等待，当出现下述情况，则表示域名配置成功；

![image-20230404103239198](image-20230404103239198.png)

接着通过域名访问网址，成功！

![image-20230404103500895](image-20230404103500895.png)