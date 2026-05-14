---
title: "免费建站：利用Cloudflare的Pages搭建网站"
date: 2021-04-18T15:19:10+08:00
draft: false
---

[Cloudflare](https://www.cloudflare.com/)推出了免费的[Pages](https://pages.cloudflare.com/)(网页)服务，类似于[Github](https://github.com/)的[Github  Pages](https://pages.github.com/) ，并提供pages.dev的二级域名，可以利用此服务部署动态前端应用程序。

![](/images/image.md_-1.png)

官方给出的示例:

[caption id="" align="alignnone" width="500"]![](/images/imageb6d8cf8d119c5b46.md_.png) 搭建很简单，需要准备：[/caption]

 	- Cloudflare账号

 	- Github账号、仓库

一个简单地示例：
#### 1.注册Cloudflare，注册过程很简单，不再展开讲；

#### 2.注册Github,并创建一个代码仓库（Repositories），仓库里的内容可以是自己的代码，也可以使用[Hexo](https://hexo.io/)等程序；

#### 3. 在Cloudflare pages中关联Github 仓库：

![](/images/imagee7fa952badcb893a.md_.png)

选择准备好的仓库，点击开始设置，

![](/images/image2eb929aa4fe6d45b.md_.png)

![](/images/imagea513811662f5bab6.md_.png)

项目名称就是二级域名的名称，例如项目名称为example，则二级域名为：example.pages.dev 。

如果项目名称重复，则cloudflare会增加唯一标识，所以提前想好一个项目名称。

构建命令根据框架预设提供了示例。

点击保存并部署。

根据代码不同，构建的时间也不同，等待部署成功后，即可访问。

更多内容可以查看官方文档：[https://developers.cloudflare.com/pages/](https://developers.cloudflare.com/pages/)

&nbsp;

&nbsp;

&nbsp;