***[[Required]]***

#内置类 

该 Readonly 会接收一个 泛型参数，并返回一个完全一样的类型，只是所有属性都会被 readonly 所修饰。

```ad-example
```ts
interface Todo {
  title: string
  description: string
}

const todo: MyReadonly<Todo> = {
  title: "Hey",
  description: "foobar"
}

todo.title = "Hello" // Error: cannot reassign a readonly property
```

```ad-success
title: Answer
```ts
type MyReadonly<T> = {
  readonly [P in keyof T]: T[P];
}
```

---
[参考文档](https://github.com/type-challenges/type-challenges/blob/main/questions/00007-easy-readonly/README.zh-CN.md)