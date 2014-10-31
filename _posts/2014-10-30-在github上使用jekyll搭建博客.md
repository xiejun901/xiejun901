---
layout: page
category : github
title: 在github上使用jekyll搭建博客
tags : [github, jekyll, 博客]
---
{% include JB/setup %}

## 购买域名，安装git，在github上建立项目空间.
参考以下博客：

[如何搭建一个独立博客——简明Github Pages与Hexo教程](http://www.jianshu.com/p/05289a4bc8b2)

[使用Github Pages建独立博客](http://beiyuu.com/github-pages/)

## 新建本地仓库
参考[一步步在GitHub上创建博客主页(2) ](http://www.pchou.info/web-build/2013/01/05/build-github-blog-page-02.html)

在磁盘上创建一个目录，该目录名与项目名同名。在该目录下启动Git Bash，输入以下命令初始化本地仓库。

	$git init
	
创建一个没有父节点的分支gh-pages,并切换到此分支：

	$git checkout --orphan gh-pages
	
##上传本地仓库的内容

	$ git add .                    ,添加所有文件目录，在高版本中，需要用git add -A(git add --all)或者 --ignore-removal,否则的话，在本地删掉的文件会被忽略。
	$ git add -u                   ,将本地所有改动（包括删除和修改）标记，如果删除了文件的话要用这个命令。
	$ git commit -m "first post"   ,将暂存的改动提交到本地仓库，并写入本次提交的注释是”first post“
	$ git remote add origin https://github.com/username/projectName.git    ,添加远程仓库路径，即将远程仓库的路径添加叫作origin。
	$ git remote rm origin         ,删除origin
	$ git push origin gh-pages     ,将本地仓库内容上传到github仓库中
	
##其他的一些git命令

	$ git add -A                    ,或者--all，添加所有更改。在新版本中，$git add .会忽略已经删除的文件，对删除的文件不作更改。

##jekyll的安装

jekyll本身基于ruby开发，所以先要安装ruby。

###安装Ruby
1. 前往[Ruby安装程序下载地址](http://rubyinstaller.org/downloads/) ,下载合适的版本。 安装程序，安装目录不要带空格。勾选“Add Ruby executables to your PATH”
可以自动添加环境变量。
2. 打开命令提示行来检测Ruby是否安装成功

	$ ruby -v

###安装DevKit
1. 前往[Ruby安装程序下载地址](http://rubyinstaller.org/downloads/) ,下载对应版本的DevKit。
2. 解压至某文件夹，如C:\rubydevkit.执行以下命令可以进入到文件夹，生成config.yml，安装DevKit。
	
		$ cd C:\rubydevkit
		$ ruby dk.rb init
		$ ruby dk.rb install
		
###安装jekyll
1. 将安装的源设置为国内的淘宝镜像

		$ gem sources --remove https://rubygems.org/
		$ gem sources -a https://ruby.taobao.org/
		$ gem sources -l
		
2. 运行以下命令安装jekyll
		
		$ gem install jekyll
		
##Pygments的安装
Jekyll里默认的语法高亮插件是Pygments。它需要安装Python并在网站的配置文件_config.yml里将highlighter的值设置为pygments。

###安装python

1. 前往[python下载地址](http://www.python.org/download/)下载合适版本的python，进行安装。
2. 添加应用程序路径到环境变量
3. 输入以下命令检验python是否安装成功。
		
		$ python –-version
		$ python -V
		
###安装Easy Install
1. 下载[ez_setup.py](https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py)并用python运行此文件。
2. 添加Python Scripts的路径至环境变量
3. 检查Easy Install版本，确保安装成功。
		
		$ easy_install –-version
		
###安装 Pygments
	
	$ easy_install Pygments
	
以上内容参考[在 Windows 上安装 Jekyll---by 曾屹](http://cn.yizeng.me/2013/05/10/setup-jekyll-on-windows/)

参考jekyll官网[Jekyll Quick-start guide](http://jekyllrb.com/docs/quickstart/)执行以下命令可以快速测试jekyll
	
	$ jekyll new myblog
	$ cd myblog
	$ jekyll serve	
	
在浏览器中打开[http://localhost:4000](http://localhost:4000)，更多jekyll相关内容可参考[http://jekyllrb.com/](http://jekyllrb.com/)

关于语法高亮设置，需要生成.css并添加。参考[Jekyll 中的语法高亮：Pygments](http://havee.me/internet/2013-08/support-pygments-in-jekyll.html),
[Jekyll - Syntax highlighting](http://truongtx.me/2012/12/28/jekyll-bootstrap-syntax-highlighting/)

一个配置jekyll的例子[我的jekyll配置和修改](http://blog.javachen.com/2013/08/31/my-jekyll-config/)

