### 1. 利用 `wrapper` 函数包裹.  ^1
```tsx
// 包裹 validator, resolve: 结束校验, catch: 继续校验后续
export function wrapperValidator(validator: AntValidatorNormal, newRule: AntValidatorNormal): AntValidatorNormal {
  return (...rest) => {
	return newRule(...rest).catch(() => {
	  return validator(...rest);
	});
  }
}

export function switchCloseResolve(switchOn?: boolean) {
  // 没有开启的消息, 可以不用校验, 直接保存
  return !switchOn ? Promise.resolve() : Promise.reject();
}

// wrapperValidator(validator, () => switchCloseResolve(switchOn), ...)
```