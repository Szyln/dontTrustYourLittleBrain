---
title: "IIFE"
tag: 
- 
---
# IIFE (Immediately Invoked Function Expression)
> `()` 中只能放 Expression，不可以放 Statement

宣告後直接執行函式

>在 JS 的 library source code 常見到
```js
// 匿名也可以
(function fn(name) {
	console.log(name);
// argument 包在 () 也行
})("Sam");
```

```js
// 表達式也可以
const fn = function (name) {
	console.log(name);
})("Sam")
```
>[函式表達式 function expression](函式表達式%20function%20expression.md)

#js #function 