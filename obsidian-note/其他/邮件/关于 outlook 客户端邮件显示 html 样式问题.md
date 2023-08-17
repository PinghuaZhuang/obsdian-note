#EDM
## [[Table]] 样式问题
## 对齐方式
`text-align` 只有在 `td` 元素上有效果.
1. 一行多列: 对应一个 `tr` 多个 `td`.
2. 多行单列: 对应多个 `tr` 或者 `table`, 单个 `td`.
## 边距
`padding` `margin` 无效. 必须使用 `td` 设置边距才行. 
## disaplay
只在 `table` 上生效(`block`, `inline-block`).
## 图片显示
+ 在客户端, windows自带的邮件上, 外部链接是支持的, 不过客户端是需要用户点击行为, 触发下载后, 才能看到图片. 
+ windows自带的邮件上显示不了 base64的图片. 
综上, 图片链接最好是外部链接, 避免图片显示不了的问题. 
