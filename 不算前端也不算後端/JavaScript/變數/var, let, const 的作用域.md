---
title: "var, let, const 的作用域"
tag: 
- 
---
# let, const, var 的差異
>- [【直播記錄】JavaScript 那個 let, const, var 到底差在哪？](https://www.youtube.com/watch?v=FGdKdn_CnWo)
>- [block(javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)

|比較內容|var|let|const|
|-|-|-|-|
|[[block]] 內使用會造成[全域污染](全域污染.md)（不形成 [Scope 作用域](Scope%20作用域.md)）|非嚴格：是 / 嚴格：否|否|否|
|顯示在 windows 上 |是|否|否|
|受非同步影響|是|否|否|
|[Hoisting](Hoisting.md)|有|無|無|
|[[暫時性死區(TDZ)]]|無|有|有|
|再宣告（re-declaration）|可|否|否|
|再指派（re-assignment 賦值）|可|可|否|
|未[[初始化(initializer)]]就使用|可|可|否|




## [Function Execution Context](Function%20Execution%20Context.md) 中宣告
- [Function Execution Context](Function%20Execution%20Context.md) 會形成 [Scope 作用域](Scope%20作用域.md)：[Function Scope](Function%20Scope.md)
- var, let, const 都不會全域污染

## Block 中宣告
>[Block Scope](Block%20Scope.md)

## 再宣告
- var 可以被重複宣告，會有 [[Hoisting]] 狀況
- let 不行，會有錯誤提示

### var
var 可以重複宣告，會 hoisting，作用域內若在宣告前被呼叫，不會產生錯誤提示
```javascript
function fn(a) {
	console.log(a);	// 2.log 1
	var a = 2;		// 3.重複宣告
	console.log(a);	// 4.log 2
}
fn(1);				// 1.在外部先指定 a = 1
```

### let
let 不能重複宣告，不會 hoisting，作用域內若在宣告前被呼叫，**會**產生錯誤提示（[[暫時性死區]]）
```
// let 在被宣告前呼叫的話
Cannot access 'a' before initialization
```
會產生暫時性死區，不能執行
```javascript
function fn(a) {
	console.log(a);	// 2.暫時性死區，log 錯誤提示不能執行
	let a = 2;		// 3.不可重複宣告，不能執行
	console.log(a);	// 4.不能執行
}
fn(1);				// 1.外部指定 a = 1
```



## const 與 let 不同之處
````javascript
// 可重複賦值
let a = 1;
a = 2;        // 可
````
````javascript
// 不可重複賦值
const a = 1;
a = 2;        // 不可
````

## [物件傳參考](物件傳參考.md)
const 如果碰上 object 的話，單純修改裡面的內容是可以的
但直接改 const 成其他物件是不行的（物件傳參考）
```javascript
const a = {
	name: "卡斯伯",
}; 

a.name = "Ray";		// 可
```
```javascript
const a = {
	name: "卡斯伯",
}; 

a = {
	name: "ray",
}; 					// 不可
```


#js #variable

  

