---
title: hexo
tags:
  - hexo
categories:
  - 环境搭建
date: 2019-10-11 13:46:46
---

使用hexo搭建个人博客。

<!-- more -->

#### hexo运行及发布环境搭建

  在使用hexo搭建个人博客之前需先安装[Git](https://git-scm.com/downloads)和[NodeJs](http://nodejs.cn/download/)。

#### hexo安装及初始化

1. 打开命令行执行：
```
npm install hexo-cli -g
```

2. 初始化hexo项目
选择博客项目的根目录，然后执行
```
<!-- 初始化blog项目 -->
hexo init blog
<!-- 进入blog目录 -->
cd blog
<!-- 安装依赖 -->
npm install 
```
#### 本地运行
执行命令后，访问http://localhost:4000
```
hexo serve
```
#### 发布到github pages

在github设置中添加ssh-key
<!-- ![avatar](../images/hexo_sshkey.png) -->
{% asset_img hexo_sshkey.png set ssh-key %}
添加完成后，创建博客的发布仓库
{% asset_img create_repository.png 创建博客的发布仓库 %}

修改根目录下的配置文件_config.yml，添加博客发布相关配置
{% asset_img deploy.png 发布相关配置 %}

添加博客发布相关包
```
npm install hexo-deployer-git --save
```

然后执行命令，将博客发布到配置的地址
```
hexo clean 
hexo generate
hexo deploy
```
然后就可以访问xxxx.github.io查看效果

#### 配置hexo项目主题
hexo主题文件存放在themes目录下，默认主题是xxx, 你可以在[hexo主题库](https://hexo.io/themes/)，挑选一个主题用于你的博客，例如[material x](https://github.com/xaoxuu/hexo-theme-material-x)

在根目录下执行
```
<!-- 下载主题 -->
git clone https://github.com/xaoxuu/hexo-theme-material-x.git ./themes/material-x
<!-- 安装主题所需依赖-->
npm i -S hexo-generator-search hexo-generator-json-content hexo-renderer-less
```
然后在配置文件中将主题配置theme字段的值修改为material-x，这样就将主题应用于你的博客了。


