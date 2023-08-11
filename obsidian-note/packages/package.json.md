https://zhuanlan.zhihu.com/p/148795036
## alias
在项目中创建别名. 
```json
{
	"alias": {
	    "easy-moveable/resizable": "easy-moveable/resizable"
	  }
}
```

## _moduleAliases
https://juejin.cn/post/7069928369260855333

## 安装的依赖设置别名
以 query-string 库为例，假如要同时安装v6和v5，安装时执行：
```bash
npm i qs6@npm:query-string@6.x qs5@npm:query-string@5.x
```
安装完成后，可以看到 package.json 中依赖项声明为：

```json
"dependencies": {
    "qs5": "npm:query-string@^5.1.1",
    "qs6": "npm:query-string@^6.11.1"
}
```

在 node_modules 目录中，可以看到有 `qs6` 和 `qs5` 两个目录，证明确实安装了两个版本的 query-string 库。

# imports 和 exports
[掘金](https://juejin.cn/post/7219478427299971130)
https://github.com/jkrems/proposal-pkg-exports/