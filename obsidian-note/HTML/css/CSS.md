# 深色模式
```css
html[theme='dark-mode'] img{
  filter: invert(1) hue-rotate(180deg);
}
```

# 解决多个空格只显示一个空格的问题
1. 使用 `&nbsp;` 代替空格. 
2. 设置样式 `white-space: pre;`.

# 选择器

## [[属性选择器]]
## 其他选择器
+  `a~b` 可以选中后续 b ，但空行后的 b 也会被选中。