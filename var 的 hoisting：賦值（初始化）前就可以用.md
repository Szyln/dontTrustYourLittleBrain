---
title: "var 的 hoisting：賦值（初始化）前就可以用"
tag: 
- 
---

##  var 的 hoisting：賦值（初始化）前就可以用
> 分為兩個步驟：
> - 宣告（會 hoisting）
> - 賦值（[初始化(initializer)](初始化(initializer).md)、不會 hoisting）

- `var` hoisting 將宣告提升至該 [Scope 作用域](Scope%20作用域.md)頂端
- 賦值前使用只會跳 `undefined`，不會炸掉

> 為了程式碼穩定，你應該使用 `let`, `const` 並且希望他炸掉：[暫時性死區(TDZ)](暫時性死區(TDZ).md)

>長得有點像但不是：[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)

```javascript
console.log(a);	// 不會輸出 not defined，而是輸出 undefined 
var a = 1; 
console.log(a); // 輸出 1
```

hoisting 的效果可以解讀成
```javascript
var a; 			// hoisting
console.log(a);	// log undefined
var a = 1; 		// 賦值
console.log(a); // 輸出 1
```

