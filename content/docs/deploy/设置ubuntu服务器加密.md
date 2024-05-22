## 修改ssh默认登录端口

1. 修改SSH登录端口：

vi /etc/ssh/sshd_config

将 Port 22 改成其他的xxx端口

2. lsof -i:xxx端口 检查端口是否被占用

3. 执行开放xxx端口
```
sudo iptables -A INPUT -p tcp --dport xxx端口 -j ACCEPT
```

4. 重新启动SSH

```
cd /etc/init.d
./ssh restart
```

## 修改默认登录账户

1. 添加登录账号

```
sudo adduser your_new_user 
sudo passwd your_new_user
sudo usermod -aG sudo your_new_user
```

2. 关闭root用户的默认登录

```
vim /etc/ssh/sshd_config
PermitRootLogin no 
这一列值设置为no
```