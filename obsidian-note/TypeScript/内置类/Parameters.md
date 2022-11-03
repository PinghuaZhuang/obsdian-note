***[[ReturnType]]***

#内置类 

获取函数的所有参数. 

```ad-success
title: Answer
```ts
type MyParameters<T> = T extends (...params: infer Params) => unknown ? Params : never;
```

