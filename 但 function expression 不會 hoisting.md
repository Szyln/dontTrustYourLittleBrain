---
title: "但 function expression 不會 hoisting"
tag: 
- 
---

##  但 function expression 不會 hoisting
就算用 `var` 也不會 hoisting

```js
fn();											// error
let fn = function() {		// 不會 hoisting
	console.log("hi");
}
```
![](https://i.imgur.com/prF6nSE.png)

### 加深印象
思考一下， `var` 未[初始化(initializer)](初始化(initializer).md)] 的時候用起來是長這樣
```js
var a 
a 
// return undefined
```
但呼叫 [函式表達式 function expression](函式表達式%20function%20expression.md) 會附著`()` 
其實不一樣
```js
var a
a
var a = fn() { console.log('a') } 
// 炸掉
a()
// 寫到這邊還是炸
```