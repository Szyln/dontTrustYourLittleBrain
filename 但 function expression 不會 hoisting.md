---
title: "但 function expression 不會 hoisting"
tag: 
- 
---

##  但 function expression 不會 hoisting
就算用 `var` （`var` 會，但這個 `function` 沒有）也不會 hoisting

```js
console.log(fn)         // undefined
fn();										// fn is not a function
let fn = function() {		// 不會 hoisting
	console.log("hi");
}
```
![](https://i.imgur.com/prF6nSE.png)
