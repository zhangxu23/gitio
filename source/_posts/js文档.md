---
title: js文档
date: 2020-06-16 16:03:11
tags:
---
# js使用
## bebal 转码
[bebal 转码](https://es6.ruanyifeng.com/#docs/intro#Babel-%E8%BD%AC%E7%A0%81%E5%99%A8)


### 配置文件.babelrc
Babel 的配置文件是.babelrc，存放在项目的根目录下。使用 Babel 的第一步，就是配置这个文件。

该文件用来设置转码规则和插件，基本格式如下。

```js
{
  "presets": [
    "@babel/env",
    "@babel/preset-react"
  ],
  "plugins": []
}
```
### resets字段设定转码规则
官方提供以下的规则集，你可以根据需要安装。
```bash
#最新转码
$ npm install --save-dev @babel/preset-env
#react 转码规则
$ npm install --save-dev @babel/preset-react
```

### 下载依赖
@babel/register模块改写require命令，为它加上一个钩子。此后，每当使用require加载.js、.jsx、.es和.es6后缀名的文件，就会先用 Babel 进行转码。

```bash
$ npm install --save-dev @babel/register
```
### 引入依赖
使用时，必须首先加载@babel/register。
```bash
// main.js
require('@babel/register');
require('./index.js');
```
### 运行
就不需要手动对index.js转码了。

```bash
$ node main.js
```
需要注意的是，@babel/register只会对require命令加载的文件转码，而不会对当前文件转码。另外，由于它是实时转码，所以只适合在开发环境使用。