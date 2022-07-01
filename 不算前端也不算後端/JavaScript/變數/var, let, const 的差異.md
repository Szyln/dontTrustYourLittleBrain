---
title: "var, let, const 的差異"
tag: 
- 
---

##  var, let, const 的差異
>- [【直播記錄】JavaScript 那個 let, const, var 到底差在哪？](https://www.youtube.com/watch?v=FGdKdn_CnWo)
>- [block(javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)

|比較內容|var|let|const|
|-|-|-|-|
|[[block]] 內<br>會 [全域污染](全域污染.md) or<br> 形成 [Block Scope](Block%20Scope.md)|非嚴格：全域污染 /<br> 嚴格：作用域|作用域|作用域|
|`for(這裡的宣告) {}` 受 [[block]] 內的非同步影響|是，危|否，選我|無法再指派|
|顯示在 windows 上 |是|否|否|
|當前作用域使用後宣告 |[Hoisting](Hoisting.md) `undefined`|[[暫時性死區(TDZ)]] 炸|[[暫時性死區(TDZ)]] 炸|
|再宣告 re-declaration<br>[重複宣告一個外層的變數](重複宣告一個外層的變數.md)|可，以當前作用域為主|- ==同作用域：炸==<br>- 不同作用域：可，以當前作用域為主|- ==同作用域：炸==<br>- 不同作用域：可，以當前作用域為主|
|再指派（re-assignment 賦值）|可|可|炸|
|未[[初始化(initializer)]]就使用([undefined](undefined.md))|可|可|炸|

^1f3f2a

- Block 中宣告：[Block Scope](Block%20Scope.md)
- const 與 let 不同之處：是否可重新賦值
	- 改物件（[物件的傳參考特性](物件的傳參考特性.md)）內部內容不算重新賦值

> Function 中宣告：
>- [Function Execution Context](Function%20Execution%20Context.md) 會形成 [Scope 作用域](Scope%20作用域.md)：[Function Scope](Function%20Scope.md)
>- var, let, const 都不會全域污染，其實用哪個都不會影響


#js #variable

  

