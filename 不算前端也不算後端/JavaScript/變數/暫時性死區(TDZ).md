---
title: "暫時性死區(TDZ)"
tag: 
- js/variable/scope
---
## 暫時性死區 (TDZ
>與 [Hoisting](Hoisting.md) 算相反概念

暫時性死區指的是 `let`, `const` 在未宣告就使用時，使用會出現 error 的狀況

```js
function fn(a) {
	console.log(a) // TDZ error，不會 log 1
	let a = 2			 // 宣告（不會 hoisting）
	console.log(a) // TDZ 已經炸掉了不會 log
}

fn(1)						 // 炸掉
```
![](https://i.imgur.com/YiciyW8.png)

>[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)
