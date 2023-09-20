# 非H5
## 获取dom

[知乎](https://zhuanlan.zhihu.com/p/403039139#:~:text=%E6%88%91%E4%BB%AC%E7%9F%A5%E9%81%93%E5%9C%A8vue%E4%B8%AD%E8%A6%81%E6%83%B3%E6%8B%BF%E5%88%B0dom%E5%85%83%E7%B4%A0%EF%BC%8C%E9%9C%80%E8%A6%81%E5%9C%A8dom%E5%85%83%E7%B4%A0%E6%8C%82%E8%BD%BD%E5%88%B0%E9%A1%B5%E9%9D%A2%E4%B8%8A%E6%89%8D%E5%8F%AF%E4%BB%A5%EF%BC%8C%E4%B9%9F%E5%B0%B1%E6%98%AF%E5%9C%A8mounted%20%28%29%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E4%B8%AD%EF%BC%8C%E5%90%8C%E7%90%86%E5%9C%A8uniapp%E4%B8%AD%E9%9C%80%E8%A6%81%E5%9C%A8%E9%A1%B5%E9%9D%A2%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E4%B8%ADonReady,%28%29%20%E6%88%96%E8%80%85%E7%BB%84%E4%BB%B6%E5%91%A8%E6%9C%9Fmounted%20%28%29%E5%86%85%E8%8E%B7%E5%8F%96%E6%89%8D%E6%9C%89%E6%95%88)

# H5
## 路由条件
[网上资料](https://blog.51cto.com/u_15920212/5963957#:~:text=uni.navigateTo%20%28OBJECT%29%E2%80%8B%20%E2%80%8B,%E4%BF%9D%E7%95%99%E5%BD%93%E5%89%8D%E9%A1%B5%E9%9D%A2%EF%BC%8C%E8%B7%B3%E8%BD%AC%E5%88%B0%E5%BA%94%E7%94%A8%E5%86%85%E7%9A%84%E6%9F%90%E4%B8%AA%E9%A1%B5%E9%9D%A2%EF%BC%8C%E4%BD%BF%E7%94%A8%E2%80%8B%20%E2%80%8Buni.navigateBack%E2%80%8B%20%E2%80%8B%E5%8F%AF%E4%BB%A5%E8%BF%94%E5%9B%9E%E5%88%B0%E5%8E%9F%E9%A1%B5%E9%9D%A2%E3%80%82)
+ navigateTo的events参数是当前页面监听. 
+ navigateTo的success回调可以像打开的页面传递数据. 
	+ `(res) => res.eventChannel.emit(...);`
+ 打开页面监听事件: `eventChannel.on(...);`
+ 打开页面回传数据: `eventChannel.emit(...)`

获取事件总线
```js
const eventChannel = this.$scope?.eventChannel ?? this.getOpenerEventChannel();
```
