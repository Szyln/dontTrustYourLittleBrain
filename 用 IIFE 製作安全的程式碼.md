## 用 IIFE 製作安全的程式碼
>[複數 script 時的執行環境](複數%20script%20時的執行環境.md)

框架中為了解決這個問題會這樣寫
```js
// script1
let a = 2

// script2
// IIFE
(function(name) {
	let a = 1;
	console.log(a, name)
})('Sam')

// 把程式碼用 function scope 包起來防止互相影響

```