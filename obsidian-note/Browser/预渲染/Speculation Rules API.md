```html
<script type="speculationrules"> 
  {  
    "prefetch": [  
      {  
        "source": "list",  
        "urls": ["next.html", "next17.html"]  
      }  
    ]  
  }  
</script>
```

```html
<script type="speculationrules">  
  {  
    "prerender": [  
      {  
        "source": "list",  
        "urls": ["next.html", "next17.html"]  
      }  
    ]  
  }  
</script>
```

```js
// 判断浏览器是否支持 speculationrules  
if (HTMLScriptElement.supports &&  
    HTMLScriptElement.supports('speculationrules')) {  
  const specScript = document.createElement('script');  
  specScript.type = 'speculationrules';  
  specRules = {  
    prerender: [  
      {  
        source: 'list',  
        urls: ['/17.html'],  
      },  
    ],  
  };  
  specScript.textContent = JSON.stringify(specRules);  
  console.log('添加预渲染规则: 17.html');  
  document.body.append(specScript);  
}
```