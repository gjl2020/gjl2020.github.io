---
title: Github + Jekyll 实现博客搭建
categories: [环境配置]
tags: [博客搭建]     # TAG names should always be lowercase
---

# Github + Jekyll 实现博客搭建

## 一、准备阶段
### 1.注册Github账号
### 2.安装git
### 3.安装Github桌面版
图形化界面操作，避免使用git指令。

## 二、环境配置
以下环境配置使得在本机就能够将个人博客搭建起来，便于我们修改页面配置或发布文章时进行测试。   

### 1.Ruby
下载链接：https://rubyinstaller.org/downloads/

64位机器选择x64 Devkit版本

![ruby下载页面](/assets/img/2022-7-26/1.png)

在cmd中检测是否安装成功

![ruby](/assets/img/2022-7-26/2.png)


### 2.RubyGems
RubyGems 是 Ruby 的一个包管理器，它提供一个分发 Ruby 程序和库的标准格式，还提供一个管理程序包安装的工具。

Ruby安装完成后，在cmd中执行

``
gem -v               
``

检测gem是否安装。如果显示gem版本，则安装完毕，否则可前往 rubygems.org/pages/download 下载压缩包。

将压缩包解压，在cmd中前往解压目录，执行

``
ruby setup.rb
``

![rubygem](/assets/img/2022-7-26/3.png)

在cmd中查看gem版本，检测gem是否安装成功。


### 3.Jekyll
使用gem安装Jekyll

``
gem install jekyll
``

检测Jekyll是否安装成功

``
jekyll -v
``

注：使用 gem install 下载安装需要较长时间，可能会长时间没有反应，属于正常现象，所以安装Jekyll和Bundler需要耐心等待。

### 4.Bundler
使用gem安装Bundler

``
gem install bundler
``

## 三、博客搭建

### 1.Fork Jekyll模板
chirpy是一个Jekyll模板

![chirpy](/assets/img/2022-7-26/4.png)

前往 https://github.com/cotes2020/jekyll-theme-chirpy 

fork 该模板，并将项目命名为 

``
<GH_USERNAME>.github.io
``

GH_USERNAME 为Github用户名

然后使用Github桌面版将 <GH_USERNAME>.github.io 克隆到本地仓库

### 2.博客本地环境搭建

在本地仓库目录中打开gitbash

![gitbash1](/assets/img/2022-7-26/5.png)

执行

``
bash tools/init.sh
``

![gitbash2](/assets/img/2022-7-26/6.png)


从cmd中进入本地仓库目录，并执行

``
bundle
``

安装依赖。注意，bundle执行的时间很长，会很久没有反应，耐心等待。如果bundle命令执行到
![bundle1](/assets/img/2022-7-26/8.png)

无反应，可尝试按回车。最终成功安装结果如下：

![bundle2](/assets/img/2022-7-26/7.png)

继续，在该目录下执行

``
bundle exec jekyll s
``

![jekyll1](/assets/img/2022-7-26/9.png)

在浏览器中打开 http://127.0.0.1:4000/

![jekyll2](/assets/img/2022-7-26/10.png)

### 3.博客线上部署
