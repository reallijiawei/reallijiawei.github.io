---
layout: post
title: jekyll+github pages搭建博客的过程
categories: jekyll
tags: [jekyll]
---



# jekyll+github pages搭建博客的过程

jekyll是一个静态网页生成的工具，可以把markdown等格式的文件转换成静态的网页，生成了之后可以在本地直接通过http://localhost:4000来查看静态的网页，也可以关联到github pages上。下面来介绍这两种方式。

## 本地搭建博客

参考：[jekyll官网](https://www.jekyll.com.cn/)。

环境准备：

![](/assets/images/1.PNG)

准备好环境之后按照如下步骤操作：

![](/assets/images/2.PNG)

一切顺利的话，就能在本地预览博客了。如果不会/不想自己设置博客格式的话，可以在这里找一个喜欢的模板fork一下，再克隆下来：[博客模板](http://jekyllthemes.org/ )。再在项目根目录执行bundle exec jekyll serve。

但是正如生活一样，想要一点问题都没遇到也是不太可能。

你可能会遇到，4000端口被占用的问题，因为jekyll默认使用4000端口。这时用netstat |find "4000"查看哪个进程占用了这个端口，把他杀掉就行。或者在jekyll项目的_config.yml文件中加上`port: xxx`，可以修改默认的端口为空闲的端口就可以了。

也可能会遇到执行bundle exec jekyll serve的时候，有很多gem库的版本不对，这时可以用gem install -v 1.0.1 xxx来安装指定版本的库



## 公网访问博客

我们搭一个博客肯定不想只能在本地访问， 想要在公网访问的话，就得把这个静态网站挂载到github pages上

github pages是github提供的一个托管静态网页的功能。原理就是，我们既然可以通过特定的url访问github自己的主页或项目，就相当于是github已经提供了一个公网上你专属的域名和数据库，这不就是一个博客服务器需要的两个东西吗？

可能会遇到在本地网页是正常显示的，但是到了github上就格式就乱了。解决办法是：

`在_config.yml中把baseurl改为`

`baseurl=""`

最简单的实践：

建立一个空项目，把项目的名称改成 用户名.github.io，在项目根目录搞一个index.html的文件，里面写上hello world，这样这个项目就是一个静态网站了。开启github pages后就可以通过https://用户名.github.io来访问这个项目。

怎么把jekyll搭建的静态网站挂载到github pages上呢？

把我们之前fork的别人已经写好的jekyll博客模板，远端的项目名字改成用户名.github.io就可以了。就是这样简单。



## 写博客

项目的_posts目录是存放博客的位置，我们在这里添加一个新的文件，格式是年-月-日-xxxx.md。然后文件的开头要加一个YAML代码块，来指示该博文的格式，标题，标签等。

![/assets/images/3.PNG]()

然后下面就可以用markdown的语法来写博文了，写完可以本地bundle exec jekyll serve，看下效果，也可以直接push到远端，让github pages渲染。我比较懒，就直接push了。

