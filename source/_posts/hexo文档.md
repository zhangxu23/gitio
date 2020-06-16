---
title: hexo文档
date: 2020-06-16 16:16:16
tags:
---
## hexo使用
### 安装 Hexo
```bash
npm install -g hexo-cli
```
安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```
### 新建文章
```bash
$ hexo new [layout] <title>
```
### 准备工作
首先要安装好git然后配置ssh 这个必须使用git才可以生成
```bash
cd ~/. ssh 
#如果没有用下面命令创建
ssh-keygen -t rsa -C "邮件地址"
```
找到.ssh\id_rsa.pub文件，记事本打开并复制里面的内容，打开你的github主页，进入个人设置 -> SSH and GPG keys -> New SSH key：将刚复制的内容粘贴到key那里，title随便填，保存。
### 测试是否更改安装ssh
```bash
$ ssh -T git@github.com 
```
输入yes，然后会看到：hi 就是成功了。
### 全局配置
```bash
$ git config --global user.name "liuxianan"// 你的github用户名，非昵称
$ git config --global user.email  "xxx@qq.com"// 填写你的github注册邮箱
```
### 部署

首先创建自己名字的github.io
#### 修改配置文件
```yml
deploy:
  type: git
  repo: git@github.com:zhangxu23/zhangxu23.github.io.git
  branch: master
```
#### 安装git部署插件

```bash
$ npm i hexo-deployer-git --save
```
#### 一键部署
```bash
$ hexo deploy
```
#### 后续部署
您可执行下列的其中一个命令，让 Hexo 在生成完毕后自动部署网站，两个命令的作用是相同的。

```bash
$ hexo generate --deploy
$ hexo deploy --generate
```
### 修改主题
下载hexo主题 在官网或者github
```bash
#切换到主题目录
$ cd themes
#depth 指定下载最新版本
$ git clone https://github.com/iissnan/hexo-theme-next.git --depth=1
#不切换文件夹
git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
```
### 修改配置文件
```bash
theme: hexo-theme-next
```
