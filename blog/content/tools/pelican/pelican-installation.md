Title: pelican installation
Date: 2015-03-01 23:10
Category: tools
Tags: 201503, pelican, python, git 
Author: adyvei
Summary: pelican的安装和github发布


pelican的安装
================

依赖包
---------

feedgenerator, jinja2, pygments, docutils, pytz, blinker, unidecode, six,
python-dateutil, markupsafe, markdown, ghp-import

安装
----------
```bash
pip install pelican 
pip install markdown
pip install ghp-import
```

在github建个人博客
-------------------------
  以"adyvei.github.io"建立repository，签出，进入并建立"blog"目录和如下设置".gitignore"
```bash
blog/*
!blog/content
!blog/content/*
```

master提交新加的"blog"目录
```bash
git add .
git commit -m "init empty blog"
```

将已有的博客复制到"blog"目录，并建立代码分支
```bash
cd blog
pelican-quickstart
git checkout -b source
git add .
git commit -m "add blog"
```

将博客发布到"master"
```bash
$ pelican content
$ ghp-import -b master output
$ git checkout master
$ git push --all
```

pelican使用
----------
```bash
pelican content
cd output
python -m http.server 80
```

github使用
=========================

常用命令
------------
```bash
$ git clone https://github.com/hnlaomie/backup
$ cd backup
$ git add .
$ git commit -m 'first commit'
$ git push origin master
```
参考
==================
* <http://ntanjerome.org/blog/how-to-setup-github-user-page-with-pelican/>
* <http://blogs.skicelab.com/maurizio/unicode-common-pitfalls.html>
* <http://ntanjerome.org/blog/how-to-setup-github-user-page-with-pelican/>
* <http://moparx.com/2014/04/adding-search-capabilities-within-your-pelican-powered-site-using-tipue-search/>
