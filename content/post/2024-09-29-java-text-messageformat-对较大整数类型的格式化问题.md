---
title: "java.text.MessageFormat 对较大整数类型的格式化问题"
date: 2024-09-29T07:51:10+08:00
draft: false
---

MessageFormat 的参数是数字类型时，当数字超过 3 位数字以上时，每隔 3 位会多增加一个的逗号。

#### 解决办法

1.第一种方法是将数字转为字符串，然后再进行格式化

```
 MessageFormat.format("{0}", String.valueOf(IntSomething));
```

2. 第二种方法是增加 MessageFormat 的 FormatStyle

```
MessageFormat.format(" {0, number, #}", IntSomething);

```