---
title: "修改mysql的max_allowed_packet大小"
date: 2020-11-21T14:37:02+08:00
draft: false
---

mysql中参数max_allowed_packet的值过小，会造成导入sql数据过慢，或报错等异常情况。通常情况下，max_allowed_packet默认值为1048576，单位是B，也就是1MB（1024×1024），最大值为1G，也就是1073741824（1024×1024×1024），超过最大值实际可用1073741824，可以通过两种方式进行修改。

&nbsp;
### 1.临时修改

#### 1.查看mysql的max_allowed_packet大小：

```
show variables like 'max_allowed_packet';
```

#### 2.临时修改mysql的max_allowed_packet大小：

```
set global max_allowed_packet = 1024 * 1024 * 1024;
```

### 2.永久修改

#### mysql5.*的数据库:

在数据库安装目录下，打开my.in配置文件，搜索[mysqld]，在[mysqld]下添加一行
```
`max_allowed_packet = 1073741824`
```

#### mysql8.*的数据库:

my.ini文件在ProgramData\MySQL\MySQL Server 8.0目录下,修改方式与mysq5.*相同。