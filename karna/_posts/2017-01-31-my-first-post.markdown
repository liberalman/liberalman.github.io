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