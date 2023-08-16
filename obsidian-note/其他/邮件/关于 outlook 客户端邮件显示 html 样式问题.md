#EDM

```ad-warning
title: 文档对齐方式
collapse: none
文档中 `<div style="text-align: center" />` 直接使用是无效的, 包括 `float` `flex` 等其他所有对齐方式, 均无效. 
```

## 对齐方式
1. 一行多列: 对应一个 `tr` 多个 `td`.
2. 多行单列: 对应多个 `tr` 或者 `table`, 单个 `td`.

## 图片显示
+ 在客户端, windows自带的邮件上, 外部链接是支持的, 不过客户端是需要用户点击行为, 触发下载后, 才能看到图片. 
+ windows自带的邮件上显示不了 base64的图片. 
综上, 图片链接最好是外部链接, 避免图片显示不了的问题. 