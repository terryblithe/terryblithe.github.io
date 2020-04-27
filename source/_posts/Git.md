---
title: Git
date: 2017/10/25 23:32:10
comments: true
tags: 
- git
- github
categories:
- git/github
---

## 一、Clone Repository

### Clone Github上的Repository

``` bash
git clone git@github.com:terryblithe/terryblithe.github.io.git # clone到当前目录下

git clone git@github.com:terryblithe/terryblithe.github.io.git target # 指定clone到目标目录下
```

## 二、管理分支

### (一)、查看分支

#### 1、查看本地分支

``` bash
git branch
* master  # * 标识的是你当前所在的分支
```

<!-- more -->

#### 2、查看远程分支

``` bash
git branch -r
```

#### 3、查看所有分支

``` bash
git branch -a
```

### (二)、创建和使用分支

#### 1、本地创建新的分支

``` bash
git branch [branch name]
```
例如:
``` bash
git branch hexo # 创建hexo分支
```

#### 2、切换到新的分支
``` bash
git checkout [branch name]
```
例如:
``` bash
git checkout hexo # 切换分支到hexo
```

#### 3、创建 + 切换分支整合命令
``` bash
git checkout -b [branch name] # 创建并切换分支组合命令
```
例如:
``` bash
git checkout -b hexo
```
该命令相当于一下操作：
``` bash
git branch hexo

git checkout hexo
```

### (三)、将新分支推送到远程仓库
``` bash
git push origin [branch name]
```
例如:
``` bash
git push origin hexo # 将hexo分支推送到远程仓库
```

### (四)、删除本地分支
``` bash
git branch -d [branch name]
```
例如:
``` bash
git branch -d hexo # 删除hexo分支
```

### (五)、删除Github远程分支
``` bash
git push origin :[branch name]
```
例如:
``` bash
git push origin :hexo  # 删除hexo分支，分支名前的冒号(:)代表删除
```

