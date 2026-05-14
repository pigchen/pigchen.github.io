---
title: "debian10安装mariadb"
date: 2021-05-06T11:58:32+08:00
draft: false
---

这里用apt-get自动安装mariadb，debian10默认将数据库换成了mariadb，使用与mysql无区别
### 安装命令

使用如下命令查询当前linux发行版的信息：

`lsb_release -a`

安装命令：

`apt install mariadb-server mariadb-client`
### 配置root的密码

`sudo mysql_secure_installation`

然后提示是否修改root密码，输入Y修改。

**New password后输入新密码，密码是不显示的，正常输入即可；回车后，再次输入密码。**

![](/images/image.png)