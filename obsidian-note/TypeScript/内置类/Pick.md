***[[Omit]] [[Partial]]***

#内置类 

从类型 T 中选择出属性 K，构造成一个新的类型。

```ad-example
```ts
interface Todo {
  title: string
  description: string
  completed: boolean
}

type TodoPreview = MyPick<Todo, 'title' | 'completed'>

const todo: TodoPreview = {
    title: 'Clean room',
    completed: false,
}
```

```ad-success
title: Answer
```ts
// 可以理解 keyof Todo 是一个列表, K 是其中一种可能性
type MyPick<T, K extends keyof T> {
	[P in K]: T[P]
}
```

---
[参考文档](https://github.com/type-challenges/type-challenges/blob/main/questions/00004-easy-pick/README.zh-CN.md)