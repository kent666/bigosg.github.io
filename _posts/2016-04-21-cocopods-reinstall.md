---
layout: post
title: Cocopods的卸载与重新安装
date: 2016-04-21 21:17:35
category: "iOS"
---

前段时间用HomeBrew把Cocopods升级到 **1.0.0.beta.3**，今天在项目中执行 **pod update** 时提示了错误。

{% highlight java %}
[!] Invalid `Podfile` file: [!] The specification of `link_with` in the Podfile is now unsupported, please use target blocks instead..
{% endhighlight %}

查看cocopods 安装的地址，并删除程序包
{% highlight shell %}
$ which pod // 查看安装地址
$ sudo rm -rf <path>
{% endhighlight %}
