+ `table` `tr` 元素不支持 `padding` 属性
+ `tr` `td` 元素不支持 `margin` 属性
解决方法:
1. 使用表格自带的属性
	1. cellspacing  相当于为表格设置margin属性
	2. cellpadding  相当于为表格设置padding属性
2. 使用css的属性
	1. cellspacing 属性使用border-collapse设置。
	2. cellpadding 属性使用td 的padding设置
