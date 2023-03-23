# 利用 `mask` 属性镂空
也可以利用 css 的 [mask](https://developer.mozilla.org/zh-CN/docs/Web/CSS/mask) 属性 + 图片.
```jsx
<svg>
	<defs>
	  <mask id="ant-tour-mask-:raa:">
		<rect x="0" y="0" width="100vw" height="100vh" fill="white"></rect>
		<rect
		  x="1.2vw"
		  y={
			document.body.offsetHeight -
			(359 / 375) * document.body.offsetWidth +
			'px'
		  }
		  rx="2"
		  width="37.33vw"
		  height="24.53vw"
		  fill="black"
>	   </rect>
	  </mask>
	</defs>
	<rect
	  x="0"
	  y="0"
	  width="100%"
	  height="100%"
	  fill="rgba(0,0,0,0.7)"
	  mask="url(#ant-tour-mask-:raa:)"
    ></rect>
</svg>
```
## 效果图
![[Pasted image 20230322161147.png]]