---
title: "centos7设置firewall防火墙，开放（禁用）端口"
date: 2020-11-12T14:30:52+08:00
draft: false
---

centos7设置firewall防火墙，开放或禁用端口

#### 安装firewall

yum install -y firewalld
yum install -y firewall-config 
#### 启动

```
systemctl start firewalld # 启动
systemctl status firewalld #查看firewalld当前状态
systemctl enable firewalld # 开机启动
systemctl stop firewalld # 关闭
systemctl disable firewalld # 取消开机启动
```

#### 添加端口

```
firewall-cmd --zone=public --add-port=5000/tcp --permanent  #对外网全部开放
firewall-cmd --zone=public --permanent --add-rich-rule &#039;rule family=ipv4 source address=192.168.0.1/24 port port=22 protocol=tcp accept&#039; #添加端口开放
firewall-cmd --permanent --remove-rich-rule &#039;rule family=ipv4 source address=192.168.0.1/2 port port=5000 protocol=tcp accept&#039; #删除端口开放
```

（--permanent永久生效，没有此参数重启后失效）

#### 禁用端口

```
firewall-cmd --zone=public --remove-port=80/tcp --permanent
```

#### 重新载入配置生效

```
firewall-cmd --reload
```

#### 查看开放端口列表

```
firewall-cmd --list-ports
```