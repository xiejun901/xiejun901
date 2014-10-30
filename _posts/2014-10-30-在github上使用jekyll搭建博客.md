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

	$ git add .                    ,添加所有文件目录
	$ git add -u                   ,将本地所有改动（包括删除和修改）标记，如果删除了文件的话要用这个命令。
	$ git commit -m "first post"   ,将暂存的改动提交到本地仓库，并写入本次提交的注释是”first post“
	$ git remote add origin https://github.com/username/projectName.git    ,添加远程仓库路径，即将远程仓库的路径添加叫作origin。
	$ git remote rm origin         ,删除origin
	$ git push origin gh-pages     ,将本地仓库内容上传到github仓库中
	
##其他的一些git命令

 
