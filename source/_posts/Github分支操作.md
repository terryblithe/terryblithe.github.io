---
title: Github分支操作
---

## 一、Clone Repository

### Clone Github上的Repository

``` bash
$ git clone git@github.com:terryblithe/terryblithe.github.io.git
```

## 二、管理分支

### (一)、查看分支

#### 1、查看本地分支

``` bash
$ git branch
  * master
  * 标识的是你当前所在的分支
```
#### 2、查看远程分支

``` bash
$ git branch -r
```

#### 3、查看所有分支

``` bash
$ git branch -a
```

### (二)、创建和使用分支

#### 1、本地创建新的分支

``` bash
$ git branch [branch name]
-> $ git branch hexo
```

#### 2、切换到新的分支
``` bash
$ git checkout [branch name]
-> $ git checkout hexo
```

#### 3、创建+切换分支整合命令
``` bash
$ git checkout -b [branch name]
-> $ git checkout -b hexo
该命令相当于一下操作：
-> $ git branch hexo
-> $ git checkout hexo
```

### (三)、将新分支推送到Github
``` bash
$ git push origin [branch name]
-> $ git push origin hexo
```

### (四)、删除本地分支
``` bash
$ git branch -d [branch name]
-> $ git branch -d hexo
```

### (五)、删除Github远程分支
``` bash
$ git push origin :[branch name]
->分支名前的冒号代表删除
-> $ git push origin :hexo
```