```ad-warning
不支持 `contenthash`
```
## import.meta.glob
异步懒加载
```js
// tree-shaking
const modules = import.meta.glob('./dir/*.js', { import: 'setup', eager: true })
```

## import.meta.globEager
同步加载

## 关于@vitejs/plugin-legacy 不支持库模式
[issues1639](https://github.com/vitejs/vite/issues/1639)
😂 还是没有达到预期的效果, 最终生成的代码中包含有 reqire('corejs....')
原因: esbuild 不会转换为 es5，而且无法配置让 babel 可以处理 ts 甚至转换为 es5。
解决办法: 通过 esbuild (vite) 在生成的代码上运行 babel。

```js
// vite.config.js (e.g)
const { getBabelOutputPlugin } = require('@rollup/plugin-babel');

export default {
  build: {
    rollupOptions: {
      plugins: [
        /**
         * Running Babel on the generated code:
         *  https://github.com/rollup/plugins/blob/master/packages/babel/README.md#running-babel-on-the-generated-code
         *
         * Transforming ES6+ syntax to ES5 is not supported yet, there are two ways to do:
         *  https://github.com/evanw/esbuild/issues/1010#issuecomment-803865232
         * We choose to run Babel on the output files after esbuild.
         *
         * @vitejs/plugin-legacy does not support library mode:
         *  https://github.com/vitejs/vite/issues/1639
         */
        getBabelOutputPlugin({
          allowAllFormats: true,
          presets: [
            [
              '@babel/preset-env',
              {
                useBuiltIns: false, // Default：false
                // Exclude transforms that make all code slower
                exclude: ['transform-typeof-symbol'],
                // https://babeljs.io/docs/en/babel-preset-env#modules
                modules: false,
              },
            ],
          ],
          plugins: [
            /**
             * Extract the helper function.
             */
            [
              '@babel/plugin-transform-runtime',
              {
                corejs: false,
                // version: require('@babel/runtime').version,
              },
            ],
          ],
        }),
      ],
    },
  },
};
```