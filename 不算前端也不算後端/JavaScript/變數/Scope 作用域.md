---
title: "Scope 作用域"
tag: 
- 
---
# Scope 作用域
>- [mdn](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

有三種作用域，形成作用域的時候，可以防止上層讀取內部的宣告（var, let, const, function）

> 作用域的存在是為了防止[全域污染](全域污染.md)



## 類型
> Scope 的生成時機與 [Execution Context](Execution%20Context.md) 有關

- Global Scope
- Function Scope ^50eb8d
- [[block]] Scope

|作用域類型|var|let|const|
|-|:-:|:-:|:-:|
|Global|O|O|O|
|Function|O|O|O|
|Block|==非嚴格模式 X== / 嚴格模式 O|O|O|

## Global Scope
在 Global 宣告的變數與函式，在哪裡都可以讀取
```js
// 誰都可以調用 Global 宣告的變數
var age = 14;
let name = "Sam";
const height = 150;

// 誰都可以調用 Global 宣告的 Function
function myName() {
	console.log(name);
}

myName();		// log "Sam"
```

## Function Scope
Function Scope 裡面宣告的變數與函式，只能在函式內使用
```js
function myName() {
	// 只有這個 Function 可以使用
	var age = 14;
	let name = "Sam";
	const height = 150;
	
	console.log(`${age}, ${name}, ${height}`); // log 14, Sam, 150
}

myName();			// log 14, Sam, 150
console.log(name);	// error
```

## [[block]] Scope
Block Scope 的變數，只能在 block (loop, if)裡面讀取
使用 var 會全域污染
```js
var x = 1;
for (var i = 0; x < 10; x++) {
	console.log(x);
}
console.log(x);			// x = 10 全域污染
```

#js #variable #scope