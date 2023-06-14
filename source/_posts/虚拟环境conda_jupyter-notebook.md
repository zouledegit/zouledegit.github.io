---
title: conda虚拟环境
date: 2023-06-14 01:07:34
tags:
---

一、conda创建虚拟环境(win10系统中，已安装anaconda3)
===========================

```bash
# 查看所有环境列表(两种方法)
$ conda env list
$ conda info -e
```

## 1. 创建虚拟环境

```bash
# 建立名为 your_env_name ，python版本为 X.X 的虚拟环境
$ conda create -n your_env_name python=X.X

# 启动虚拟环境
$ conda activate your_env_name

# 关闭虚拟环境
$ conda deactivate

# 删除虚拟环境
$ conda remove -n your_env_name --all

# 在虚拟环境中安装包，三种方法
$ conda install [package_name]
$ pip install [package_name]
## 在base环境下
$ conda install -n your_env_name [package_name]

# 删除虚拟环境中包，三种方法
$ conda remove [package_name]
$ pip uninstall [package_name]
## 在base环境下
$ conda remove -n your_env_name [package_name]

# clone虚拟环境
$ conda create -n env_name1 --clone env_name2 
```

## 2. 在虚拟环境中使用 `jupyter notebook` ，方法1

```bash
# 在虚拟环境安装 ipykernel 包
$ conda install ipykernel

# 查看jupyter kernel 列表
$ jupyter kernelspec list
# 将当前虚拟环境写入 jupyter notebook 的kernel中，并且可修改 notebook 显示名称
$ python -m ipykernel install --user --name env_name --display-name "name(jupyter显示名称)"
# 删除kernel
$ jupyter kernelspec remove kernelname

# 在当前环境安装 notebook
$ pip install notebook

# 进入 notebook
$ jupyter notebook
```



## 在虚拟环境中使用 `jupyter notebook` ，方法2（推荐）

```bash
# 在虚拟环境安装 ipykernel 包
$ conda install ipykernel

# 在虚拟环境安装 nb_conda
$ conda install nb_conda

# 进入 notebook
$ jupyter notebook
```

