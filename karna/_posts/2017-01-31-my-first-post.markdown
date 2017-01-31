---
layout: post
title:  "Example socho"
description: Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Duis vehicula tincidunt lacus nec fringilla. Morbi molestie fringilla laoreet. Vestibulum venenatis ante in imperdiet venenatis. 
date:   2016-06-13 10:51:47 +0530
categories: jekyll update
img: image-6.jpg
categories: [one, two]
color: BF360C
author: webjeda
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/



    ---
    layout: post
    title: My First Post
    ---
    这是我的第一篇博客
搭建本地Jekyll环境
最近用github搭建了个博客，正好也学习一下markdown语法，由于markdown写完后不是立即可见，所以每次写完文章都要经过在线调试，而在线调试就得上线文章，每次上线都得重复git add， git commit， git push这三步。非常的繁琐。就想怎么样能够本地调试文章，就上网搜了下，发现可以安装jekyll本地环境，下面就来说说我的安装步骤，安装过程中也出现了不少问题，我的安装环境是ubuntu 12.04 。
1. 安装ruby
yum install ruby-devel
2. 去掉官方ruby源，改用国内淘宝源，速度快

	gem sources --remove http://rubygems.org/
	gem sources -a https://ruby.taobao.org
 
 
4. 安装jekyll
gem install jekyll
5. 如果上一步安装过程中没有安装rdoc, rdiscount, kramdown等，可以执行下面步骤安装
[plain] view plain copy 在CODE上查看代码片派生到我的代码片
$ sudo gem install kramdown  
$ sudo gem install rdoc  
$ sudo gem install rdiscount  
6. 上面步骤执行完后，本地的jekyll环境就搭建完成了，进入你博客的目录，运行下面的命令启动
[plain] view plain copy 在CODE上查看代码片派生到我的代码片
$ jekyll server  
之后会有提示，访问http://0.0.0.0:4000就可以啦。



ruby编译scss出现invalid GBK错误
问题描述
在windows7上面，通过ruby编译scss时，发现编译报错，内容如下：
Conversion error: Jekyll::Converters::Scss encountered an error while converting 'css/main.scss':
                         Invalid GBK character "\xE3" on line 315
虽然给出来了报错的原因，但是尼玛，main.scss总共也没有315行啊，而且并没有中文注释什么的。查找一番之后才发现，这里编译器报错的位置不一定是scss中的位置，也有可能是你在scss中引用了其他库中含有中文字符。我在scss中引入了字体文件，文件中包含了中文字符

解决办法
1.在ruby的安装目录下找到engine.rb文件，目录格式如D:\ruby\Ruby21\lib\ruby\gems\2.1.0\gems\sass-3.4.15\lib\sass在文件中添加一行Encoding.default_external = Encoding.find('utf-8')
在require语句结束处，如：

require 'sass/media'
require 'sass/supports'
module Sass   
Encoding.default_external = Encoding.find('utf-8')

2.在scss文件的头部加一行@charset "utf-8"


如何让jekyll服务可以在局域网中访问
jekyll搭建自己的博客非常方便，通过jekyll serve -w可以持续监控文件的修改情况、编译成HTML并通过HTTP服务给本机（localhost）进行访问。

Server address: http://127.0.0.1:4000/

Server running... press ctrl-c to stop.
由于jekyll将地址绑定到了127.0.0.1，导致局域网的其它机器并不能访问它的服务。但实际上只要改变运行jekyll的参数就可以了。

$ jekyll serve -w --host=0.0.0.0

Server address: http://0.0.0.0:4000/

Server running... press ctrl-c to stop.
这样就可以通过该机器的IP地址访问网站了。


jekyll serve --watch -w --host=192.168.0.4



http://blog.csdn.net/u014015972/article/details/50497254