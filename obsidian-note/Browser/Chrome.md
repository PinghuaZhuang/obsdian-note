# 控制台过滤
使用正则, 空格分隔 `-/[React\sIntl]/ -/Warning:\sCan't\sperform/`

## 不同页面共享数据
1. localStorage
2. [ShareWorker](https://developer.mozilla.org/zh-CN/docs/Web/API/SharedWorker)
3. websocket ??

## 浏览器的线程和进程
[掘金](https://juejin.cn/post/7053974933931556900)

进程:
1. 浏览器主进程, 如标签, 书签等. 
2. 插件.
3. GPU
4. 渲染

线程:
1. 事件
2. 定时
3. http
4. GUI
5. JS 引擎