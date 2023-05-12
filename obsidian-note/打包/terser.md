压缩代码

## 注释
可以吧 @ 替换成 #
```text
/*@__INLINE__*/ - forces a function to be inlined somewhere.
/*@__NOINLINE__*/ - Makes sure the called function is not inlined into the call site.
/*@__PURE__*/ - Marks a function call as pure. That means, it can safely be dropped.
```

连续赋值会导致 `/*#**PURE***/` 失效.