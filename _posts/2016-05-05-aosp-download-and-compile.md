---
layout: post
title: Android 6.0下载与编译
date: 2016-05-05 17:22:00
category: "Android"
---

Android 6.0已经推出，更新了许多新的特性，而最好的学习方法就是直接阅读源码。所以最先想到的是下载最新的源码包。

### 环境
- 系统：OS X 10.11.4
- git : 2.6.4
- make : 3.81
- 移动硬盘

### 获取源码
从清华[AOSP镜像](https://mirrors.tuna.tsinghua.edu.cn/help/AOSP/)下载初始包（大小24GB）：

{% highlight shell %}
$ wget http://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/aosp-latest.tar # 下载初始化包
{% endhighlight %}

下载完成后，做文件MD5校验：

{% highlight shell %}
$ openssl md5 aosp-latest.tar
{% endhighlight %}

输出结果和[checksum.txt](https://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/checksum.txt)比对，结果一致。

创建一个区分大小写的android卷：
{% highlight shell %}
$ hdiutil create -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 80g -volname android /Volumes/Samsung_T1/android.dmg // 移动硬盘Samsung_T1
{% endhighlight %}

生成位置 /Volumes/Samsung_T1/android.dmg.sparseimage。双击打开android卷，将源码拷贝到android卷中，解压源码：

{% highlight shell %}
$ tar xf aosp-latest.tar
{% endhighlight %}

同步最新源码：
{% highlight shell %}
$ cd AOSP   # 解压得到的 AOSP 工程目录
$ repo sync
{% endhighlight %}

### 编译源代码
在AOSP目录下执行如下命令：

{% highlight shell %}
$ source build/envsetup.sh // 设置环境变量
$ make -j4 // 执行编译选项
{% endhighlight %}

报错：
{% highlight shell %}
build/core/config.mk:618: *** Error: could not find jdk tools.jar at /System/Library/Frameworks/JavaVM.framework/Versions/Current/Commands/../lib/tools.jar, please check if your JDK was installed correctly.  Stop.
{% endhighlight %}

修改Java环境变量：
{% highlight shell %}
$ JAVA_HOME=`/usr/libexec/java_home -v 1.8`
$ PATH=${JAVA_HOME}/bin:$PATH
{% endhighlight %}

再执行编译选项，报错：

{% highlight shell %}
Unsupported curl, please use a curl not based on SecureTransport
{% endhighlight %}

[解决方法](http://stackoverflow.com/questions/33318756/while-i-make-the-source-of-android-6-0-it-failed)是要用openssl重新编译一个curl。

{% highlight shell %}
$ ./configure --prefix=/usr/local/curl --with-ssl=/usr/local/Cellar/openssl/1.0.2d_1
$ make
$ make install
{% endhighlight %}

设置curl环境变量
{% highlight shell %}
$ sudo vim /etc/paths
{% endhighlight %}

在文件开头添加/usr/local/curl/bin,保存退出。再一次执行编译命令，报错：
{% highlight shell %}
FAILED: /bin/bash out/target/common/obj/JAVA_LIBRARIES/framework_intermediates/dex-dir/classes.dex.rsp
Out of memory error (version 1.2-rc1 'Carnac' (296000 4ba365ab8a3d2c7e55c3428f919af59e687258fa by android-jack-team@google.com)).
GC overhead limit exceeded.
Try increasing heap size with java option '-Xmx<size>'.
Warning: This may have produced partial or corrupted output.
[  0% 23/13788] Building with Jack: out/target/common/obj/JA...IBRARIES/android-support-v4-donut_intermediates/classes.jack
ninja: build stopped: subcommand failed.
make: *** [ninja_wrapper] Error 1
{% endhighlight %}

执行：
{% highlight shell %}
$ java -Xmx3072M -Xms2048M -XshowSettings:all
{% endhighlight %}

再一次执行编译命令：
{% highlight shell %}
[ 99% 4568/4570] Target system fs image: out/target/product/generic/obj/PACKAGING/systemimage_intermediates/system.img
Running:  mkuserimg.sh out/target/product/generic/system out/target/product/generic/obj/PACKAGING/systemimage_intermediates/system.img ext4 system 1610612736 -D out/target/product/generic/system -L system out/target/product/generic/root/file_contexts.bin
make_ext4fs -T -1 -S out/target/product/generic/root/file_contexts.bin -L system -l 1610612736 -a system out/target/product/generic/obj/PACKAGING/systemimage_intermediates/system.img out/target/product/generic/system out/target/product/generic/system
Creating filesystem with parameters:
    Size: 1610612736
    Block size: 4096
    Blocks per group: 32768
    Inodes per group: 8192
    Inode size: 256
    Journal blocks: 6144
    Label: system
    Blocks: 393216
    Block groups: 12
    Reserved block group size: 95
Created filesystem with 1487/98304 inodes and 105421/393216 blocks
[100% 4570/4570] Install system fs image: out/target/product/generic/system.img
out/target/product/generic/system.img+ maxsize=1644333504 blocksize=2112 total=1610612736 reserve=16610880
[100% 4570/4570] Checking build with Jack: out/target/common/obj/APPS/EmailTests_intermediates/jack.check.timestamp
{% endhighlight %}

成功，输出目录为/Volumes/Android/AOSP/out/target/product/generic，包含**system.img**、**ramdisk.img**、**userdata.img**等。

### 查看源码

在AOSP根目录执行:
{% highlight shell %}
$ make idegen && development/tools/idegen/idegen.sh
{% endhighlight %}

 用Android Studio打开生成的android.ipr文件阅读源码。

 参考：

 - http://source.android.com/source/initializing.html
 - https://source.android.com/source/jack.html#using_jack_in_your_android_build
 - https://android.googlesource.com/toolchain/jack/+/ub-jack/server/jack-server/etc/jack
 - https://code.google.com/p/android/issues/detail?id=194027
 - https://seewhy.me/2016/01/01/aospcompilation/
 - http://taobaofed.org/blog/2016/05/05/new-compiler-for-android/
