---
title: "Hoisting"
tag: 
- 
---
## 提昇 Hoisting
- `function` 跟 `var` **宣告**會被提升到**該[Scope 作用域](Scope%20作用域.md)**的頂部
- [初始化(initializer)](初始化(initializer).md)（賦值）之後就不會 Hoisting
- 發生的時間點 [Execution Context](Execution%20Context.md) 的 [Creation Phase](Creation%20Phase.md)
- 電腦記憶體會先分配給 `function`, `var` 的宣告（lexical declaration: let, const, function expression 沒有），之後才會開始跑程式碼

### 範例
- [var 的 hoisting](var%20的%20hoisting.md)
- [function 宣告的 hoisting](function%20宣告的%20hoisting.md)

> let, const, function expression 不會 hoisting

### 不會 hoisting 的部分(lexical declaration)
- `let`
- `const`
- function expression

```js
fn();						// error
let fn() = function() {		// hoisting
	console.log("hi");
}
```

#js #variable #scope