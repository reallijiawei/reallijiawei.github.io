---
layout: post
title: jekyll+github pages搭建博客的过程
categories: jekyll
tags: [jekyll]
---



# jekyll+github pages搭建博客的过程

jekyll是一个静态网页生成的工具，可以把markdown等格式的文件转换成静态的网页，生成了之后可以在本地直接通过http://localhost:4000来查看静态的网页。

github pages是github提供的一个托管静态网页的功能。原理就是，我们既然可以通过特定的url访问github自己的主页或项目，就相当于是github已经提供了一个公网上你专属的域名和数据库，这不就是一个博客服务器需要的两个东西吗？

最简单的实践：

建立一个空项目，把项目的名称改成 用户名.github.io，在项目根目录搞一个index.html的文件，里面写上hello world，这样这个项目就是一个静态网站了。开启github pages后就可以通过https://用户名.github.io来访问这个项目。



上面建立的网站太过简单了，如果我们想生成样式好看的博客网站，就需要用jekyll了。

可以直接fork别人已经写好的jekyll博客模板：

[]: http://jekyllthemes.org/

,fork完之后把项目名字改成用户名.github.io就可以了。这样自己的博客就搭好了，就这样简单。



