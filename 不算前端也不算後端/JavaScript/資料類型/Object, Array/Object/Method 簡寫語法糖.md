---
title: "Method 簡寫語法糖"
tag: 
- 
---
# Method 簡寫語法糖
原本的 [Object](Object.md) 字面值的屬性都是以 [[Key-Value Pair]] 的形式出現，ES6 的語法糖中， function 可以如下簡寫：
### 原本寫法
```js
const obj1 = {
	fn1: function() {
		return this;
	};
}
```
### ES6 語法糖
```js
const obj1 = {
	funName() {			// 語法糖
		return this;
	};
}
```

## 箭頭函式沒有這個語法糖
這是傳統的 function 寫法語法糖，與 [[箭頭函式]] 不同，與[this 的指向](this%20的指向.md) 有關，不能混為一談
```js
var a = 1

const obj1 = {
	fn: () => {
		console.log(this);
	},
}
obj1.fn() // this 指 window object
```

#js #function #advanceJs 