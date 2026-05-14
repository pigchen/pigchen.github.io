---
title: "debian安装、配置JAVA环境"
date: 2020-11-22T12:24:58+08:00
draft: false
---

Java包括Java Runtime Environment（JRE）和Java Development Kit（JDK）。 如果只是需要运行java程序，只安装JRE即可，如果需要开发JAVA程序，则需要安装JDK。

### 1.安装OpenJDK

通过apt命令直接安装。

#### 安装OpenJDK 8 JDK

sudo apt install default-jdk
#### 安装OpenJDK 8 JRE

```
sudo apt install default-jre
```

### 1.安装Oracle Java

#### 首先，下载Java存档：

```
curl -L -b &quot;oraclelicense=a&quot; -O http://download.oracle.com/otn-pub/java/jdk/8u181-b13/96a7b8442fe848ef90c96a2fad6ed6d1/jdk-8u181-linux-x64.tar.gz
```

上面的命令将自动接受Oracle许可证并下载Java tarball。

#### 接下来，为Java安装创建一个目录

sudo mkdir /usr/local/oracle-java-8
#### 将Java .tar.gz文件解压缩到先前创建的目录：

```
sudo tar -zxf jdk-8u181-linux-x64.tar.gz -C /usr/local/oracle-java-8
```

#### 解压缩文件后，运行以下命令以创建新的替代方案：

```
sudo update-alternatives --install &quot;/usr/bin/java&quot; &quot;java&quot; &quot;/usr/local/oracle-java-8/jdk1.8.0_181/bin/java&quot; 1500
sudo update-alternatives --install &quot;/usr/bin/javac&quot; &quot;javac&quot; &quot;/usr/local/oracle-java-8/jdk1.8.0_181/bin/javac&quot; 1500
sudo update-alternatives --install &quot;/usr/bin/javaws&quot; &quot;javaws&quot; &quot;/usr/local/oracle-java-8/jdk1.8.0_181/bin/javaws&quot; 1500
```

### 3.设置默认版本

#### 检查默认Java版本，包括：

```
java -version
```

输出内容:

java version &quot;1.8.0_181&quot;
Java(TM) SE Runtime Environment (build 1.8.0_181-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.181-b13, mixed mode)
如果我们在服务器上安装了多个Java版本，我们可以使用update-alternatives系统更改默认版本：

sudo update-alternatives --config java
输出内容:

There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                            Priority   Status
------------------------------------------------------------
* 0            /usr/local/oracle-java-8/jdk1.8.0_181/bin/java   1500      auto mode
  1            /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081      manual mode
  2            /usr/local/oracle-java-8/jdk1.8.0_181/bin/java   1500      manual mode

Press  to keep the current choice[*], or type selection number:
出现提示时输入数字，然后按Enter键。

### 4.卸载Java

执行命令

```
sudo apt remove default-jre
```