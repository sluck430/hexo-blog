---
title: IDEA报告Address already in use: bind
date: 2023-05-05 11:25:55
tags: IDEA；
---

# 

# IDEA无法打开，出现java.util.concurrent.CompletionException: java.net.BindException: Address already in use: bind

今天启动IDEA时候，弹出了"Start Failed"错误提示窗口，关键内容如下：

```
java.util.concurrent.CompletionException: java.net.BindException: Address already in use: bind
...
Caused by: java.net.BindException: Address already in use: bind
...
```

这里是错误提示的截图 ↓ 

![Snipaste_2023-05-05_10-42-46](Snipaste_2023-05-05_10-42-46.jpg)

图：IDEA错误窗口截图



遂搜索了一下解决方案，部分内容参考来自以下博客：

1. [Idea无法正常启动问题排查 - 安培昌浩 - 博客园 (cnblogs.com)](https://www.cnblogs.com/masahiro/p/16080670.html)

2. [IDEA未正确关闭导致Address already in use: bind | 会打篮球的程序猿 (lzhpo.com)](http://www.lzhpo.com/article/165)



# 1. 问题分析

根据博客（1），在Itellij IDEA官方论坛有相关问题的解释

>it tries to bind on the fires available port between 6942 and 6991,this exception is thrown if IDE was not able to bind on any of the ports in this range
>
>IDE启动时会尝试寻找端口号6942~6991之间的第一个可用端口并进行绑定，如果该范围中（50个端口号）的任何端口都无法绑定，则会报告该异常

![img](https://img2022.cnblogs.com/blog/1564514/202203/1564514-20220331102930137-1814988376.png)

其实就是 **端口被占用** 问题。

仔细回忆了一下，我上次使用电脑干了些啥：

> 1. IDEA仍在运行时没正确关闭，就直接点了关机强制结束了（没正常关闭可能导致端口没放开？）
>
> 2. 下载安装了Mysql/Docker容器（可能Hyper-V的启动会占用了端口？）





# 2. 解决方案

两步走解决这个问题：

1. **通过 管理员身份 运行 命令行窗口（cmd）**

![Snipaste_2023-05-05_10-45-58](Snipaste_2023-05-05_10-45-58.jpg)

2. **执行命令 重置 winsock**

在cmd窗口中（管理员身份）**输入以下命令：**

```
netsh winsock reset
```

然后就会出现以下显示，示意你必须重启电脑，然后我们重启电脑再打开IDEA就可以了

![image-20230505105609441](image-20230505105609441.png)



注意：有的朋友此处可能会失败，可以再尝试一下 管理员身份执行以下命令：

```
net stop winnat
net start winnat
```



3. **正常启动IDEA**

大功告成！