保存元素位置不变的情况下, 修改 `transform-origin`
```js
// <script src="https://unpkg.com/rematrix"></script>
const demo = document.querySelector('#demo');
const transform = Rematrix.fromString(getComputedStyle(demo).transform);

const newMx = [
	Rematrix.translate(-150, -150),
	transform,
	Rematrix.translate(150, 150),
].reduce(Rematrix.multiply);
```