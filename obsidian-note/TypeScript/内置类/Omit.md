***[[Pick]]  [[Partial]]***

#内置类 #TODO

不使用 Omit 实现 TypeScript 的 Omit<T, K> 泛型。

```ad-example
```ts
interface Todo {
  title: string
  description: string
  completed: boolean
}

type TodoPreview = MyOmit<Todo, 'description' | 'title'>

const todo: TodoPreview = {
  completed: false,
}
```

```ad-success
title: Answer
```ts
type MyOmit<T, K> = {
  [P in keyof K]: K[P] extends T ? never : K[P];
};
```

---
[参考文档](https://github.com/type-challenges/type-challenges/blob/main/questions/00003-medium-omit/README.zh-CN.md)