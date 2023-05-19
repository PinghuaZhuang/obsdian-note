让你多个页面相互通信
[简单使用](https://juejin.cn/post/7173701460947894308?utm_source=gold_browser_extension)
# Quick Start
创建
```js
const sharedWorker = new SharedWorker('worker.js');
```
接收
```js
sharedWorker.port.onmessage = (e) => { console.log(e.data); };
```
发送
```js
sharedWorker.port.postMessage('hello');
```