## `useSyncExternalStore`
创建全局的状态响应
[参考文档](https://juejin.cn/post/7056588815170813965)

## `useDeferredValue`
不紧急的部分延迟渲染.

## 路由
### 路由阻塞 history.block
例如路由跳转前, 提示用户是否继续跳转.
```js
// 注册一个简单的提示消息，在用户离开当前页面之前，该消息将显示给用户。
const unblock = history.block('Are you sure you want to leave this page?');

// 或者在需要时使用返回消息的函数。
history.block((location, action) => {
  //location和action参数指示我们要转换到的位置以及如何到达那里。

  //一个常见的用例是防止用户在有表单尚未提交时离开页面。
  if (input.value !== '') return 'Are you sure you want to leave this page?';
});

// 要停止blocking transitions，请调用block（）返回的函数。
unblock();
```