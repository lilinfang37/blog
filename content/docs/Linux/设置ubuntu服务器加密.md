---
title: 设置ubuntu服务器加密
description: 
date: 2024-5-23
weight: 1
---

## 修改ssh默认登录端口

1. 修改SSH登录端口：
```bash
vi /etc/ssh/sshd_config
```
将 Port 22 改成其他的xxx端口

2. `lsof -i:xxx端口` 检查端口是否被占用

3. 执行开放xxx端口
```bash
sudo iptables -A INPUT -p tcp --dport xxx端口 -j ACCEPT
```

4. 重新启动SSH

```bash
cd /etc/init.d
./ssh restart
```

## 修改默认登录账户

1. 添加登录账号

```bash
sudo adduser your_new_user 
sudo passwd your_new_user
sudo usermod -aG sudo your_new_user
```

2. 关闭root用户的默认登录

```bash
vim /etc/ssh/sshd_config
PermitRootLogin no 
这一列值设置为no
```