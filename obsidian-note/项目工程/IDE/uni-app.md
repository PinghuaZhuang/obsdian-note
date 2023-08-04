# 配置 `babel`
## 配置 polyfills
- [uni-app-polyfills-presets](https://www.npmjs.com/package/uni-app-polyfills-presets)
- [uni-app-core-js](https://www.npmjs.com/package/uni-app-core-js)
```bash
npm install uni-app-polyfills-presets@1.0.0  
npm install uni-app-core-js@1.0.0
```
然后在`./babel.config.js`里写
```javascript
module.exports = {  
  presets: [  
    // 上面的代码略...  
    [  
      'module:uni-app-polyfills-presets',  
      {  
        // 如果写usage那么将是按实际使用情况引入兼容库  
        // 参数具体解释请前往https://babeljs.io/docs/en/babel-preset-env查看  
        useBuiltIns: 'usage'  
      }  
    ]  
    // 下面的代码略...  
  ],  
  plugins  
}
```