---
title: 部署Hugo服务
description: 
date: 2024-5-23
weight: 1
---


## 安装 Hugo

检查系统架构：uname -i

安装Dart Sass前置模块
```bash
sudo snap install dart-sass
```

1. 去到 [Release](https://github.com/gohugoio/hugo/releases) 页面中下载最近版本（建议使用extended版本）

https://github.com/gohugoio/hugo/releases/download/v0.125.4/hugo_extended_0.125.4_linux-amd64.tar.gz

2. 解压缩之后，将 Hugo.exe 放置在系统环境变量中
```bash
 export PATH=$PATH:/home/lilnfh/my-env
```


3. 检查版本：hugo version

## 安装 Go

去到[官网](https://go.dev/dl/)下载安装包版本（go1.22.3.windows-amd64.msi），一键安装，省事

```bash
$ rm -rf /usr/local/go && tar -C /usr/local -xzf go1.22.3.linux-amd64.tar.gz

vim ~/.bashrc 
export PATH=$PATH:/usr/local/go/bin
export PATH=$PATH:/home/lilnfh/my-env/
 source ~/.bashrc
go version
```

参考：https://go.dev/doc/install

检查安装成功: go

## 安装 nodejs

1. 选择最近的一个版本：https://nodejs.org/download/release/

2. 解压之后，添加 node.exe 目录到环境变量

逐步操作，并查看英文介绍
```bash
# installs nvm (Node Version Manager)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# 上一步骤安装之后，有英文提示，执行英文提示语句即可
# download and install Node.js
nvm install 21

# verifies the right Node.js version is in the environment
node -v # should print `v21.7.3`

# verifies the right NPM version is in the environment
npm -v # should print `10.5.0`
```

3. 检查版本：node -V

## npm 更换为国内源

npm config set registry https://registry.npm.taobao.org

https://registry.npm.taobao.org

## 安装 Git

自行查找教程

### 生成秘钥(ssh key)

```bash
检查本地是否有SSH Key存在 
ls -al ~/.ssh

ssh-keygen -t rsa -C "your_email@example.com"

cat /home/user/.ssh/id_rsa.pub

```

https://stackoverflow.com/questions/68775869/message-support-for-password-authentication-was-removed


### 需要使用token登录

设置用户名和邮件
```bash
git config --global user.name "your_github_username"
git config --global user.email "your_github_email"
git config -l
```

设置token缓存
```bash
git config --global credential.helper cache
```

清除token缓存
```bash
git config --global --unset credential.helper
git config --system --unset credential.helper
```

## 安装 docsy


## ubuntu上VScode的安装与配置

下载：https://github.com/cdr/code-server/releases

解压：
```bash
tar -zxvf [你的code-server压缩文件名] -C /opt/
```

链接：
```bash
ln -s /opt/[你的code-server目录名]/code-server /usr/local/bin/code-server
```

运行：
```bash
code-server --bind-addr 0.0.0.0:[你的端口号]
```

参考：https://blog.csdn.net/day_to_die/article/details/105990565

