---
title: python虚拟环境
date: 2023-06-15 17:30:00
tags:
---
一、Virtualenv - Python虚拟环境(ubuntu系统中)
===========================

## 知识点

+ 默认包管理的问题
+ 虚拟环境的建立

## Virtualenv-官网

https://virtualenv.pypa.io/en/latest/

## 安装

```bash
$ pip install virtualenv
$ virtualenv --help
```

## 建立第一个虚拟环境

```bash
$ cd [venv_root]
# 建立虚拟环境
$ virtualenv myweb
# 启动虚拟环境
$ . myweb/bin/activate
# 在虚拟环境中安装包
$ pip install flask
$ pip list
# 推出虚拟环境
$ deactivate
```

## 建立第二个虚拟环境

```bash
$ cd [venv_root]
$ virtualenv mydeep
$ . mydeep/bin/activate
$ pip list
$ pip install numpy
$ deactivate
```

## 包导出与安装

```bash
$ cd [venv_root]
$ pip list

# 生成该环境的requirments.txt文件
$ pip freeze > requirements.txt

$ cat requirements.txt
$ virtualenv mydev
$ . mydev/bin/activate
$ pip list

# 在新环境下安装别的环境包
$ pip install -r requirements.txt
$ pip list
$ deactivate
```

## 课程文件

https://gitee.com/komavideo/LearnVirtualenv

## 小马视频频道

http://komavideo.com



二、pipenv - 给人用的Python开发管理工具（ubuntu系统中）
===================================

## 知识点

+ pipenv是更加便捷的Python项目管理工具

## 网站

http://pipenv.org/

## 在线体验

https://rootnroll.com/d/pipenv/

## 安装

```bash
$ pip install pipenv
$ pipenv --version
```

## 第一个工程项目

```bash
$ mkdir myweb
$ cd myweb

# 项目初始化，会自动安装几个基础包，在当前项目生成Pipfile和Pipfile.lock两个文件，随机生成虚拟目录名称
$ pipenv install

$ cat Pipfile
$ pip list

# 激活该虚拟环境
$ pipenv shell
# 不激活虚拟环境也可以，通过 pipenv run 执行当前工程已有虚拟环境的命令，如
$ pipenv run pip list

$ pip list
# 查看该虚拟环境安装目录
$ pipenv --venv
# 查看该虚拟
$ pipenv graph
# 退出当前虚拟环境
$ exit
# 安装开发专用包
$ pipenv install --dev requests
$ cat Pipfile

# 删除虚拟环境
$ pipenv --rm
```

## 团队内项目共享

### Pipfile

将建立好的Pipfile文件直接拷贝给项目组的其他成员，可迅速完成开发环境的搭建。

```bash
$ mkdir myweb1
$ cd myweb1
$ wget http://192.168.1.1/myweb/Pipfile
# 安装依赖库，包括开发用依赖库
$ pipenv install --dev
$ pipenv shell
$ pip list
$ exit
$ pipenv --venv
# 删除虚拟环境
$ pipenv --rm
$ pipenv --venv
```

## 代码运行

### main.py

```python
import requests
```

### 运行脚本

```bash
$ pipenv run python main.py
```

## 定义执行脚本

### Pipfile

```
[scripts]
start = "python main.py"
test = "pytest"
list = "pip list"
```

### 运行脚本

```bash
$ pipenv run python main.py
$ pipenv run start
$ pipenv run test
$ pipenv run list
```

## 课程文件

https://gitee.com/komavideo/LearnPipenv

## 小马视频频道

http://komavideo.com