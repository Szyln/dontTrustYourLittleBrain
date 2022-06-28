---
title: "Closure(Scope Chaining)"
tag: 
- 
---
# Closure 閉包 (Scope Chaining)
執行函式時，呼叫變數會依循
1. 先在函式內找
2. 到函式**被宣告**的地方找


```js
let name = "sam";

function fn() {
	let name = "alex";
	console.log(name);
}
```

#js #variable #scope