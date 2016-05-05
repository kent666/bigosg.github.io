---
layout: post
title: Android最新源码下载与编译
date: 2016-05-05 17:22:00
category: "Android"
---

Android 6.0已经推出，更新了许多新的特性，而最好的学习方法就是直接阅读源码。所以最先想到的是下载最新的源码包。

### 环境
- 系统：OS X 10.11.4
- git : 2.6.4
- make : 3.81
- curl : 7.43.0

### 下载镜像
从清华[AOSP镜像](https://mirrors.tuna.tsinghua.edu.cn/help/AOSP/)下载初始包（大小36GB），请耐心等待。

{% highlight shell %}
wget http://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/aosp-latest.tar # 下载初始化包
{% endhighlight %}
