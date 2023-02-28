## set-cookie 不生效的问题

1. 后端设置 [samesite](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Set-Cookie/SameSite).
2. 请求头添加 `Access-Control-Allow-Credentials=true`.