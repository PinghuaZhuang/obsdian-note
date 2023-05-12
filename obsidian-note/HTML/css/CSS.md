# 深色模式
```css
html[theme='dark-mode'] img{
  filter: invert(1) hue-rotate(180deg);
}
```

## 解决多个空格只显示一个空格的问题
1. 使用 `&nbsp;` 代替空格. 
2. 设置样式 `white-space: pre;`.