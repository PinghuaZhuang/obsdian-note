***[[Readonly]]***

#内置类 

```ad-success
title: Answer
```ts
/**
 * Make all properties in T required
 */
type Required<T> = {
    [P in keyof T]-?: T[P];
};
```
