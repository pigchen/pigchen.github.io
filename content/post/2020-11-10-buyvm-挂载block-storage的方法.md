---
title: "BuyVM 挂载Block Storage的方法"
date: 2020-11-10T15:11:51+08:00
draft: false
---

&emsp;购买完buyVm的vps和Block Storage存储块后需要手动将Block Storage挂载到vps上

#### 1. 列出存储块的名称

ls /dev/disk/by-id/
[![](/images/17bdea523cd510ea26f1eb287f0deab9.png)](https://img.950527.xyz/image/NRc)

*scsi-0BUYVM_SLAB_VOLUME-2761* 就是要挂载的存储块名称。

#### 2. 格式化存储块

mkfs.ext4 -F /dev/disk/by-id/scsi-0BUYVM_SLAB_VOLUME-2761 
[![](/images/51897ff5d284b1f6fda5cf585eaef191.md_.png)](https://img.950527.xyz/image/b9s)

#### 3. 创建挂载文件夹

mkdir -p /mnt/pan
#### 4. 挂载

```
mount -o discard,defaults /dev/disk/by-id/scsi-0BUYVM_SLAB_VOLUME-2761 /mnt/pan
```

#### 5. 查看挂载情况

```
df -h
```

![](https://img02.sogoucdn.com/app/a/100520146/FCFEEFAE352E49BF38E4AA93DD09C3DF)

#### 6. 开机启动

 echo '/dev/disk/by-id/scsi-0BUYVM_SLAB_VOLUME-2761 /mnt/pan ext4 defaults,nofail,discard 0 0' | sudo tee -a /etc/fstab
每个人的存储块名称都不一样，大部分是*scsi-0BUYVM_SLAB_VOLUME-* + 四位数字的形式。

如果执行完`ls /dev/disk/by-id/` 没有查询到存储块，可以去buyvm官网后台管理系统里挂载到vps上，如果挂载了还没有，就只能发工单了。