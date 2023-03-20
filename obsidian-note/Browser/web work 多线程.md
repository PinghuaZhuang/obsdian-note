💡 Work不能访问 `DOM API` 但是可以访问 `BOM API`;

worker是window对象的一个方法，可以通过以下方式来检测你的浏览器是否支持worker
```js
if (window.Worker) {…… your code ……}
```

```js
importScripts('./axios.min.js');

console.log('aixos', axios);

onmessage = function (event) { // 接收
	console.log('Received message:' + event.data);
  // postMessage('hahahah');

  axios.get('http://gwgp-hye6ycojwut.n.bdcloudapi.com/getIpInfo?ip=123.116.182.163').then((result) => {
    postMessage(result.data.data);
  })

  setTimeout(function () {
    postMessage('hahahah');
  }, 3000);
}
```

```js
let myWorker = new Worker('worker.js');
myWorker.postMessage('hello, world');

myWorker.onmessage = function (e) {
  console.log('You said: ', e.data);
};
```