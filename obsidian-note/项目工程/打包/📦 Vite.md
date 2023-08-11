```ad-warning
不支持 `contenthash`
```
## import.meta.glob
异步[[懒加载]]
```js
// tree-shaking
const modules = import.meta.glob('./dir/*.js', { import: 'setup', eager: true })
```

## import.meta.globEager
同步加载

## 关于@vitejs/plugin-legacy 不支持库模式
[issues1639](https://github.com/vitejs/vite/issues/1639)
```ad-danger
title: 打包出来的还是有问题
collapse: none

最好的解决办法还是自行引入pollyfills.
```
vite.config.js
```js
/// <reference types="vitest" />
import path from "path";
import { defineConfig } from "vite";
import packageJson from "./package.json";
import { babel } from '@rollup/plugin-babel';

const getPackageName = () => {
  return packageJson.name;
};

const getPackageNameCamelCase = () => {
  try {
    return getPackageName().replace(/-./g, (char) => char[1].toUpperCase());
  } catch (err) {
    throw new Error("Name property in package.json is missing.");
  }
};

const fileName = {
  es: `${getPackageName()}.mjs`,
  cjs: `${getPackageName()}.cjs`,
  iife: `${getPackageName()}.iife.js`,
  umd: `${getPackageName()}.umd.js`,
};

const formats = Object.keys(fileName) as Array<keyof typeof fileName>;

module.exports = defineConfig({
  base: "./",
  build: {
    lib: {
      entry: path.resolve(__dirname, "src/index.ts"),
      name: getPackageNameCamelCase(),
      formats,
      fileName: (format) => fileName[format],
    },
    rollupOptions: {
    },
  },
  plugins: [
    babel({
      babelHelpers: 'runtime',
      extensions: ['.js', '.jsx', '.es6', '.es', '.mjs', 'ts'],
    })
  ],
  // test: {}
});
```
babel.config.js
```js
module.exports = {
  presets: [
    [
      "@babel/preset-env",
      {
        modules: false,
        useBuiltIns: "usage",
        corejs: {
          proposals: true,
          version: "3.20.2",
        },
        targets: "ie >= 8",
      },
    ],
  ],
  plugins: ["@babel/plugin-transform-runtime"],
};

```