[Live Demo](https://codepen.io/old9/pen/xxQoEpG)
```html
<form id="form">
	<textarea name="text" wrap="hard" id="text">lkas dflkasj dflkja laskdj flkasjd lfkjas ldfjlaskdf laskdj fs dlkfj alskdjf laksdjf lkasjdlfj </textarea>
</form>
```

```css
textarea{
  width: 10em;
  height: 200px;
}
```

```js
console.log(new FormData(document.querySelector('#form')).get('text'))
```

![[Pasted image 20230908162649.png]]