---
title: "暫時性死區(TDZ)"
tag: 
- js/variable/scope
---
## 暫時性死區 (TDZ)

>與 [Hoisting](Hoisting.md) 算相反概念

Temporal Dead Zone，`let`, `const` 重複宣告的時候，使用會炸掉的狀況


## 對導入的參數重新宣告
```js
function fn(a) {
	console.log(a) // TDZ error，不會 log 1
	let a = 2			 // 宣告（不會 hoisting）
	console.log(a) // TDZ 已經炸掉了不會 log
}

fn(1)						 // 炸掉
```
## 在同作用域重新宣告
>[Scope 作用域](Scope%20作用域.md)
```js
function fn() {
	let a
	console.log(a) // TDZ error，不會 log 1
	a = 2			 // 宣告（不會 hoisting）
	console.log(a) // TDZ 已經炸掉了不會 log
}

fn()						 // 炸掉
```

![](https://i.imgur.com/b6JIhZ5.png)

![](https://i.imgur.com/YiciyW8.png)

>[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)
