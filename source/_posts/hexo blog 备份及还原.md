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

### 原文链接：https://blog.itswincer.com/posts/7efd2818/

## 一、[Hexo 搭建](https://hexo.io/zh-cn/docs/setup)

1. 初始化博客
    ```
    npm install hexo-cli -g
    hexo init blog
    cd blog
    npm install
    hexo server
    ```

2. 修改相关配置，配置文件 **_config.yml**

3. [将 **Hexo** 部署到 **GitHub Pages**](https://hexo.io/zh-cn/docs/github-pages)

## 二、Hexo 备份

1. 创建blog仓库，仓库名和blog域名一致：terryblithe.github.io

2. 创建两个分支：
    * **master** 保存静态页面
    * **hexo** 保存hexo源文件，设置hexo分支为默认分支

3. 将创建好的仓库clone到本地，并且将下面对应的hexo源文件的复制到terryblithe.github.io中
    ```
    _config.yml - 站点配置文件
    themes/ - 主题文件夹
    source/ - blog文章的.md文件夹
    scaffolds/ - 文章的模板
    package.json - 安装包的名称
    package-lock.json
    yarn.lock
    .gitignore - git配置文件忽略同步的文件
    ```

<!-- more -->

4. 将 **themes/xxx** 文件夹中的 **.git/** 删除，否则无法将主题文件夹push到github仓库

5. 在terryblithe.github.io文件夹中执行下面命令
    ```shell
    npm install
    npm install hexo-deployer-git --save
    ```

6. 将git分支切换到hexo分支，在hexo分支下执行下面命令，提交hexo源文件来备份blog
    ```shell
    git add .
    git commit -a -m "init"
    git push origin hexo
    ```
7. 执行下面命令，将生成静态页面并部署到github上
    ```shell
    hexo g -d
    ```

## 三、Hexo 恢复

1. 安装git，NodeJS，npm

2. 将仓库拷贝到本地
    ```shell
    git clone git@github.com:terryblithe/terryblithe.github.io.git
    ```
3. 在terryblithe.github.io文件夹中执行
    ```shell
    npm install hexo-cli -g 
    npm install
    npm install hexo-deployer-git
    ```

## 四、添加SSH-Keys

1. 生成秘钥：
    ```shell
    ssh-keygen -t rsa -C "yourname@email.com" # 一路回车，生成秘钥
    ```

2. 在 **.ssh** 目录中会生成2个密匙文件
    * **id_rsa** 私钥（千万不要泄露！！！）
    * **id_rsa.pub** 公钥

3. 登录github进行设置，**Settings -> SSH and GPG keys -> new SSH key**，添加 **id_rsa.pub** 文件中的内容
---