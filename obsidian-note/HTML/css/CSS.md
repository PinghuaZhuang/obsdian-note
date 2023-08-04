# 深色模式
```css
html[theme='dark-mode'] img{
  filter: invert(1) hue-rotate(180deg);
}
```

# 解决多个空格只显示一个空格的问题
1. 使用 `&nbsp;` 代替空格. 
2. 设置样式 `white-space: pre;` 或者 `white-space: pre-wrap`

# 选择器

## [[属性选择器]]
## 其他选择器
+  `a~b` 可以选中后续 b ，但空行后的 b 也会被选中。

# popover
chrome 114+ 支持原生的popover. 
[参考文档](https://juejin.cn/post/7238233943610032188)

# @supports
检查元素是否支持摸个属性
```css
@supports (display: flex) { 
	/* 如果支持 */ 
	/* 在这里放置针对支持该属性的样式规则 */ 
} 
@supports not (display: flex) { 
	/* 如果不支持 */ 
	/* 在这里放置针对不支持该属性的备用样式规则 */ 
}
```