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

### 获取源码
从清华[AOSP镜像](https://mirrors.tuna.tsinghua.edu.cn/help/AOSP/)下载初始包（大小24GB）：

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

### 编译源代码
在AOSP目录下执行如下命令：

{% highlight shell %}
source build/envsetup.sh // 设置环境变量
make -j4 // 执行编译选项
{% endhighlight %}

报错：
{% highlight shell %}
build/core/config.mk:618: *** Error: could not find jdk tools.jar at /System/Library/Frameworks/JavaVM.framework/Versions/Current/Commands/../lib/tools.jar, please check if your JDK was installed correctly.  Stop.
{% endhighlight %}

{% highlight shell %}
JAVA_HOME=`/usr/libexec/java_home -v 1.8`
PATH=${JAVA_HOME}/bin:$PATH
{% endhighlight %}

再执行编译选项：

报错：
{% highlight shell %}
============================================
PLATFORM_VERSION_CODENAME=REL
PLATFORM_VERSION=6.0.1
TARGET_PRODUCT=aosp_arm
TARGET_BUILD_VARIANT=eng
TARGET_BUILD_TYPE=release
TARGET_BUILD_APPS=
TARGET_ARCH=arm
TARGET_ARCH_VARIANT=armv7-a
TARGET_CPU_VARIANT=generic
TARGET_2ND_ARCH=
TARGET_2ND_ARCH_VARIANT=
TARGET_2ND_CPU_VARIANT=
HOST_ARCH=x86_64
HOST_2ND_ARCH=x86
HOST_OS=darwin
HOST_OS_EXTRA=Darwin-15.4.0-x86_64-i386-64bit
HOST_CROSS_OS=
HOST_CROSS_ARCH=
HOST_CROSS_2ND_ARCH=
HOST_BUILD_TYPE=release
BUILD_ID=MASTER
OUT_DIR=out
============================================
[1/2] choosing next stage
Choosing primary.ninja.in for next stage
[2/2] bootstrap out/soong/.bootstrap/build.ninja.in
[1/2] choosing next stage
Choosing main.ninja.in for next stage
[2/2] bootstrap out/soong/.bootstrap/build.ninja.in
ninja: no work to do.
Running kati to generate build-aosp_arm.ninja...
out/build-aosp_arm.ninja is missing, regenerating...
2016-05-09 11:01:54.710 xcodebuild[13571:127083] [MT] PluginLoading: Required plug-in compatibility UUID ACA8656B-FEA8-4B6D-8E4A-93F4C95C362C for plug-in at path '~/Library/Application Support/Developer/Shared/Xcode/Plug-ins/XcodeColors.xcplugin' not present in DVTPlugInCompatibilityUUIDs
============================================
PLATFORM_VERSION_CODENAME=REL
PLATFORM_VERSION=6.0.1
TARGET_PRODUCT=aosp_arm
TARGET_BUILD_VARIANT=eng
TARGET_BUILD_TYPE=release
TARGET_BUILD_APPS=
TARGET_ARCH=arm
TARGET_ARCH_VARIANT=armv7-a
TARGET_CPU_VARIANT=generic
TARGET_2ND_ARCH=
TARGET_2ND_ARCH_VARIANT=
TARGET_2ND_CPU_VARIANT=
HOST_ARCH=x86_64
HOST_2ND_ARCH=x86
HOST_OS=darwin
HOST_OS_EXTRA=Darwin-15.4.0-x86_64-i386-64bit
HOST_CROSS_OS=
HOST_CROSS_ARCH=
HOST_CROSS_2ND_ARCH=
HOST_BUILD_TYPE=release
BUILD_ID=MASTER
OUT_DIR=out
============================================
Checking build tools versions...
build/core/main.mk:148: ************************************************************
build/core/main.mk:149: You are building on a case-insensitive filesystem.
build/core/main.mk:150: Please move your source tree to a case-sensitive filesystem.
build/core/main.mk:151: ************************************************************
build/core/main.mk:152: *** Case-insensitive filesystems not supported.
make: *** [out/build-aosp_arm.ninja] Error 1
{% endhighlight %}

执行如下命令：
{% highlight shell %}
# hdiutil create -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 60g -volname android /Volumes/Samsung_T1/android.dmg // 移动硬盘Samsung_T1
{% endhighlight %}

生成位置 /Volumes/Samsung_T1/android.dmg.sparseimage，双击打开android卷，将AOSP目录拷贝至android卷，再一次执行编译命令，成功。
