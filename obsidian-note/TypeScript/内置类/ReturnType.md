***[[Parameters]]***

#内置类 

获取函数的返回值类型.

```ad-success
title: Answer
```ts
type MyReturnType<T> = T extends (...params: unkown[]) => infer U ? U : never; 
```