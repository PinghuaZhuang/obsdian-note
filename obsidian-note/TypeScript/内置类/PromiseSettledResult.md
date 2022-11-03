#内置类 

## 过滤 `fulfilled` 和 `rejected`.

```ts
const isFulfilled = <T,>(
	p: PromiseSettledResult<T>,
): p is PromiseFulfilledResult<T> => p.status === 'fulfilled';
```