---
title: "在不设置 Div 元素的宽度（width）的情况下，如何让 Div 元素居中？"
date: 2020-11-18T13:21:25+08:00
draft: false
---

&lt;div class=&quot;wrap&quot;&gt;
  &lt;div class=&quot;inner&quot;&gt;html ： 让 inner 居中&lt;/div&gt;
&lt;/div&gt;

```
.wrap {
  float: left; /* 自适应内容宽度 */
  position: relative;
  left: 50%; 
}
.inner {
  position: relative;
  left: -50%; 
}
```

.wrap 使用 float 是为了让 .wrap 的宽度等于 .inner 的宽度
让 .wrap 的左边在父层的中线上， 让.inner 的左边相对 .wrap 向左移动一半， 这样就可以实现 .inner 在.wrap 的父层的中间。