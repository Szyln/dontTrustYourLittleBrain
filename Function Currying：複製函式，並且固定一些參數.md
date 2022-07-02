## Function Currying：複製函式，並且固定一些參數
用 [function.bind(obj)](function.bind(obj).md) copy 一個 function ，但把他的參數固定下來用

> 跟 this 置換沒什麼關係

```js
function multiply(a, b) {
	return a * b;
}

// copy 的時候就可以導入 argument，不一定要全導完
const multipleByTwo = multiply.bind(this, 2)
// 剩下的在 function expression 中導入
console.log(multipleByTwo(10))
// log 20

```