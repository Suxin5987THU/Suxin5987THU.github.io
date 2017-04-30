---
title: Github Blog and hexo
mathjax: true
date: 2017-05-01 01:15:40
categories: Technology
tags:
	- Blog
	- hexo
	- Github
---

&emsp;&emsp;今天作为五一假期的一天，也由于最近学的命令和知识太多了，所以希望能够找一个平台记录一下。所以第一个技术文章就是怎么搭建这么一套博客。

## 第一次Github Blog 搭建过程
&emsp;&emsp;首先描述第一搭建的过程。
#### 安装git
```bash
$ sudo apt-get install git-core
```

#### 安装Node.js
具体方法也可以参照[hexo网站](https://hexo.io/docs/index.html)
这里采用通过nvm的方法进行安装，所以先执行下面命令安装nvm，再由nvm安装Node.js
```bash
$ curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | sh
$ nvm install stable
```

#### 安装hexo
```bash
$ npm install -g hexo-cli
```

#### 安装hexo的服务
```bash
$ cd (blog workspace)
$ npm install hexo-server --save
$ npm install hexo-deployer-git --save
```

#### 设置github pages
登录自己的github账号，建立对应的仓库。
这里必须要注意名字必须取为(username).github.io
注意是必须，否则会无法显示出博客网页。
然后在该仓库下创建hexo分支，并且将该分支设置为默认分支

#### 设置hexo和相关配置
由于是第一次配置，所以要初始化：
```bash
$ cd (blog workspace)
$ hexo init
```
在初始化之后就要配置相关的配置文件：*_config.yml*
这里主要要更改deploy选项
> deploy:
> &emsp;type:&ensp;git
> &emsp;repository:&ensp;git@github.com:Suxin5987THU/Suxin5987THU.github.io.git
> &emsp;branch:&ensp;master
> 这里注意冒号之后的空格，否则会出错。

#### 在设置好之后，就可以利用hexo相关命令看页面情况了
```bash
$ hexo g[enerate]  #渲染静态网页
$ hexo s[erver]    #打开本地服务器
$ hexo d[eploy]    #推送到github
```
当然相关的文件需要同步到github，主要有以下命令
```bash
$ git add -A
$ git commit -m xxx
$ git push origin hexo
```
