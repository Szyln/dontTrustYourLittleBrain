---
title: "Function Borrowing：借用方法給不同物件"
tag: 
- 
---

##  Function Borrowing：借用方法給不同物件
>[置換函式的 this 指向](置換函式的%20this%20指向.md)
>TODO [物件導向 OOP](物件導向%20OOP.md)
```js
const obj1 = {
	a: 1,
	printA: function() {
		console.log(this.a)
	}
}

const obj2 = {
	a: 2
}

// obj2 借用 obj1 的 printA method 來用
obj1.printA.apply(obj2)

```