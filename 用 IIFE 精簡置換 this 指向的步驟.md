## 用 IIFE 精簡置換 this 指向的步驟
```js
const obj1 = {}

(function(a, b) {
	console.log(this, a, b)
}).apply(obj1, [1, 2])
```