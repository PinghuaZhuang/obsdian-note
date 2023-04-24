## 定义类型 @typedef
```js
/**
 * @typedef {{-readonly [P in keyof T]: T[P];}} WriteAble
 */
```

## 使用泛型 @template
定义泛型
```js
/**
 * @template {MouseEvent} T
 */
```
传递泛型
```js
const value = decodeJSON(/** @type {number[]} */("[1,2,3]"))
```

## 代码提示配置
1. 在 `.vscode/settings.json`  添加 `"js/ts.implicitProjectConfig.checkJs": true`. 这个配置会被 `tsconf.json` / `jsconfig.json` 覆盖.
2. 在 `tsconf.json` / `jsconfig.json` 中配置 `{"compilerOptions": { "checkJs": true }}`.