## chunkhash
chunkhash根据不同的入口文件(entry)进行依赖文件解析、构建对应的chunk，生成对应的哈希值。当某个文件内容发生变动时，再次执行打包，只有该文件以及依赖该文件的文件的打包结果 hash 值会发生改变

## contenthash
contenthash 是只有当文件自己的内容发生改变时，其打包的 hash 值才会发生变动。

## fullhash
顾名思义，fullhash是全量的hash，是整个项目级别的。只要项目中有任何一个的文件内容发生变动，打包后所有文件的hash值都会发生改变。

## 排查 Tree Shaking 失效原因
https://juejin.cn/post/7216509759415271483

## [[📦 webpack 打包性能分析 TODO...]]