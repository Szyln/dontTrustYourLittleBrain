---
title: "暫時性死區(TDZ)"
tag: 
- 
---
# 暫時性死區 (TDZ)
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

#js #variable #scope