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
查找的结果是版本太高，所以需要降低Cocoapods的版本来解决第三方库的兼容问题。

- 移除pod组件

{% highlight shell %}
$ which pod   // 查看安装path，输出/usr/local/bin/pod
$ sudo rm -rf  /usr/local/bin/pod   // 移除安装包
{% endhighlight %}

- 移除 RubyGems 中的 Cocoapods程序包

查看gems本地程序包
{% highlight shell %}
$ gem list
{% endhighlight %}
输出
{% highlight shell %}
*** LOCAL GEMS ***

activesupport (4.2.5.1, 4.2.4)
addressable (2.3.8)
bigdecimal (1.2.0)
bundler (1.11.2)
CFPropertyList (2.2.8)
claide (1.0.0.beta.1, 0.9.1)
cocoapods (1.0.0.beta.3)
cocoapods-core (1.0.0.beta.3, 0.39.0)
cocoapods-deintegrate (1.0.0.beta.1)
cocoapods-downloader (1.0.0.beta.1, 0.9.3)
cocoapods-plugins (1.0.0.beta.1, 0.4.2)
cocoapods-search (1.0.0.beta.1, 0.1.0)
cocoapods-stats (1.0.0.beta.3, 0.6.2)
cocoapods-trunk (1.0.0.beta.2, 0.6.4)
cocoapods-try (1.0.0.beta.2, 0.5.1)
coffee-script (2.4.1)
coffee-script-source (1.10.0)
colorator (0.1)
colored (1.2)
diff-lcs (1.2.5)
escape (0.0.4)
ethon (0.8.1)
execjs (2.6.0)
faraday (0.9.2)
ffi (1.9.10)
fourflusher (0.3.0)
fuzzy_match (2.0.4)
gemoji (2.1.0)
github-pages (44)
github-pages-health-check (0.6.0)
highline (1.7.8)
html-pipeline (2.3.0)
html-proofer (2.6.4)
i18n (0.7.0)
io-console (0.4.2)
jazzy (0.5.0)
jekyll (3.1.1, 3.0.2)
jekyll-archives (2.1.0)
jekyll-coffeescript (1.0.1)
jekyll-feed (0.3.1)
jekyll-gist (1.4.0)
jekyll-mentions (1.0.0)
jekyll-paginate (1.1.0)
jekyll-redirect-from (0.9.1)
jekyll-sass-converter (1.4.0, 1.3.0)
jekyll-seo-tag (0.1.4)
jekyll-sitemap (0.10.0, 0.9.0)
jekyll-textile-converter (0.1.0)
jekyll-watch (1.3.1)
jemoji (0.5.1)
json (1.8.3, 1.7.7)
kramdown (1.9.0)
libxml-ruby (2.6.0)
liferaft (0.0.4)
liquid (3.0.6)
listen (3.0.5)
mercenary (0.3.5)
mini_portile2 (2.0.0)
minitest (5.8.4, 5.8.2, 4.3.2)
molinillo (0.4.2, 0.4.0)
multipart-post (2.0.0)
mustache (0.99.8)
nap (1.0.0)
net-dns (0.8.0)
netrc (0.7.8)
nokogiri (1.6.7.2, 1.5.6)
octokit (4.2.0)
open4 (1.3.4)
parallel (1.6.1)
psych (2.0.0)
public_suffix (1.5.3)
rake (10.5.0, 0.9.6)
rb-fsevent (0.9.7)
rb-inotify (0.9.5)
rdiscount (2.1.8)
rdoc (4.0.0)
redcarpet (3.3.4, 3.3.3)
RedCloth (4.2.9)
rouge (1.10.1)
rspec (3.4.0)
rspec-core (3.4.2)
rspec-expectations (3.4.0)
rspec-mocks (3.4.1)
rspec-support (3.4.1)
rubygems-update (2.5.2)
safe_yaml (1.0.4)
sass (3.4.21, 3.4.20)
sawyer (0.6.0)
sqlite3 (1.3.7)
terminal-table (1.5.2)
test-unit (2.0.0.0)
thread_safe (0.3.5)
typhoeus (0.8.0)
tzinfo (1.2.2)
xcinvoke (0.2.0)
xcodeproj (1.0.0.beta.2, 0.28.2)
yell (2.0.5)
{% endhighlight %}

发现Cocoapods的程序包
{% highlight shell %}
cocoapods (1.0.0.beta.3)
cocoapods-core (1.0.0.beta.3, 0.39.0)
cocoapods-deintegrate (1.0.0.beta.1)
cocoapods-downloader (1.0.0.beta.1, 0.9.3)
cocoapods-plugins (1.0.0.beta.1, 0.4.2)
cocoapods-search (1.0.0.beta.1, 0.1.0)
cocoapods-stats (1.0.0.beta.3, 0.6.2)
cocoapods-trunk (1.0.0.beta.2, 0.6.4)
cocoapods-try (1.0.0.beta.2, 0.5.1)
{% endhighlight %}
移除程序包
{% highlight shell %}
$ sudo gem uninstall cocoapods
$ sudo gem uninstall cocoapods-core
$ sudo gem uninstall cocoapods-deintegrate
$ sudo gem uninstall cocoapods-downloader
$ sudo gem uninstall cocoapods-plugins
$ sudo gem uninstall cocoapods-search
$ sudo gem uninstall cocoapods-stats
$ sudo gem uninstall cocoapods-trunk
$ sudo gem uninstall cocoapods-try
{% endhighlight %}
输出
{% highlight shell %}
Successfully uninstalled ...
{% endhighlight %}

- 安装指定版本的Cocoapods

{% highlight shell %}
sudo gem install cocoapods -v 0.39.0
{% endhighlight %}
报错
{% highlight shell %}
ERROR:  While executing gem ... (Errno::EPERM)
    Operation not permitted - /usr/bin/pod
{% endhighlight %}
OSX 10.11的权限问题，我们把安装路径换成/usr/local/bin，执行命令：
{% highlight shell %}
sudo gem install -n /usr/local/bin cocoapods -v 0.39.0
{% endhighlight %}
安装成功，查看版本：
{% highlight shell %}
pod --version
{% endhighlight %}
输出
{% highlight shell %}
0.39.0
{% endhighlight %}
然后在项目Podfile文件路径执行 **pod update**,完成依赖库的更新。
