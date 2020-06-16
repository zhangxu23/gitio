---
title: Python文档
date: 2020-06-16 14:47:51
tags:
---
# python文档
## pip下载速度慢出错
### 配置镜像源
#### 国内源：
清华：https://pypi.tuna.tsinghua.edu.cn/simple

阿里云：http://mirrors.aliyun.com/pypi/simple/

中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/

华中理工大学：http://pypi.hustunique.com/

山东理工大学：http://pypi.sdutlinux.org/

豆瓣：http://pypi.douban.com/simple/

### pip 命令格式：
```bash
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple 工具包
```
## jupyter notebook的安装
### 安装
```bash
pip install jupyter
```
###打开
```bash
jupyter notebook
```
### 安装插件nbextensions
```bash
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
```
