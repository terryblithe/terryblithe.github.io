---
title: Hexo Blog 备份及还原
date: 2018/05/01
comments: true
tags:
- Hexo
- 备份及还原
categories:
- Hexo
---

## 一、Hexo 备份
1. 创建blog仓库，仓库名和blog域名一致：terryblithe.github.io
2. 创建两个分支：*master*(保存静态页面)和*hexo*(保存hexo源文件),并且设置hexo分支为默认分支
3. 将创建好的仓库clone到本地，并且将之前hexo文件夹中的
    * _config.yml 站点配置文件
    * themes/ 主题文件夹
    * source/ blog文章的.md文件夹
    * scaffolds/ 文章的模板
    * package.json 安装包的名称
    * .gitignore git配置文件忽略同步的文件

    复制到terryblithe.github.io中

<!-- more -->

4. 将themes/xxx/文件夹中的.git/删除，否则无法将主题文件夹push到github仓库
5. 在terryblithe.github.io文件夹中执行npm install和npm install hexo-deployer-git
6. 在hexo分支下执行git add, git commit, git push origin hexo来提交hexo源文件来备份blog
7. 执行hexo g -d生成静态页面部署到github上

## 二、Hexo 恢复
1. 安装git，NodeJS，npm
2. 使用git clone git@github.com:terryblithe/terryblithe.github.io.git将仓库拷贝到本地
3. 在terryblithe.github.io文件夹中执行
    * npm install hexo-cli -g 
    * npm install
    * npm install hexo-deployer-git

## 三、添加SSH-Keys
1. 在终端下执行： ssh-keygen -t rsa -C "yourname@email.com"，一路回车
2. 在.ssh目录中会生成密匙对id_rsa(私钥，千万不要泄露), id_rsa.pub(公钥)两个文件
3. 登录github设置,Settings -> SSH and GPG keys -> new SSH key, 添加id_rsa.pub文件中的公钥，保存
---