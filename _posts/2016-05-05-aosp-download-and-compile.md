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

### 获取源码
从清华[AOSP镜像](https://mirrors.tuna.tsinghua.edu.cn/help/AOSP/)下载初始包（大小36GB）：

{% highlight shell %}
wget http://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/aosp-latest.tar # 下载初始化包
{% endhighlight %}

下载完成后，做文件MD5校验：

{% highlight shell %}
openssl md5 aosp-latest.tar
{% endhighlight %}

输出结果和[checksum.txt](https://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/checksum.txt)比对，结果一致。

解压源码：

{% highlight shell %}
tar xf aosp-latest.tar
{% endhighlight %}

同步最新源码：
{% highlight shell %}
cd AOSP   # 解压得到的 AOSP 工程目录
repo sync
{% endhighlight %}

报错：
{% highlight shell %}
remote: Counting objects: 88, done.        
remote: Compressing objects: 100% (63/63), done.        
remote: Total 88 (delta 30), reused 0 (delta 0)        
From https://aosp.tuna.tsinghua.edu.cn/platform/manifest
 * [new branch]      android-5.1.1_r37 -> origin/android-5.1.1_r37
 * [new branch]      android-6.0.1_r20 -> origin/android-6.0.1_r20
 * [new branch]      android-6.0.1_r24 -> origin/android-6.0.1_r24
 * [new branch]      android-6.0.1_r30 -> origin/android-6.0.1_r30
 * [new branch]      android-6.0.1_r31 -> origin/android-6.0.1_r31
 * [new branch]      android-cts-5.0_r5 -> origin/android-cts-5.0_r5
 * [new branch]      android-cts-5.1_r6 -> origin/android-cts-5.1_r6
 * [new branch]      android-cts-6.0_r5 -> origin/android-cts-6.0_r5
 * [new branch]      android-n-preview-2 -> origin/android-n-preview-2
 * [new branch]      build-tools -> origin/build-tools
   f43e64b..5a82ef6  cmake-master-dev -> origin/cmake-master-dev
 * [new branch]      gradle_2.0.0 -> origin/gradle_2.0.0
   7a37dd8..c201a1b  llvm       -> origin/llvm
   a305b38..9732d4b  master     -> origin/master
   d30ae5b..0eb3521  master-ndk -> origin/master-ndk
 * [new branch]      ndk-r12-beta1 -> origin/ndk-r12-beta1
 * [new branch]      openjdk    -> origin/openjdk
 * [new branch]      studio-2.0 -> origin/studio-2.0
   2b1ccb7..eb7124d  studio-master-dev -> origin/studio-master-dev
 * [new tag]         android-5.1.1_r37 -> android-5.1.1_r37
 * [new tag]         android-6.0.1_r20 -> android-6.0.1_r20
 * [new tag]         android-6.0.1_r24 -> android-6.0.1_r24
 * [new tag]         android-6.0.1_r30 -> android-6.0.1_r30
 * [new tag]         android-6.0.1_r31 -> android-6.0.1_r31
 * [new tag]         android-cts-5.0_r5 -> android-cts-5.0_r5
 * [new tag]         android-cts-5.1_r6 -> android-cts-5.1_r6
 * [new tag]         android-cts-6.0_r5 -> android-cts-6.0_r5
 * [new tag]         android-n-preview-2 -> android-n-preview-2
 * [new tag]         gradle_2.0.0 -> gradle_2.0.0
 * [new tag]         ndk-r12-beta1 -> ndk-r12-beta1
 * [new tag]         studio-2.0 -> studio-2.0
error: .repo/manifests/: contains uncommitted changes
{% endhighlight %}
