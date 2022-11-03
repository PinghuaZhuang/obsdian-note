#内置类 

从联合类型T中排除U的类型成员，来构造一个新的类型。

```ad-success
title: Answer
```ts
type MyExclude<T, U> = T extends U ? never : T;
```