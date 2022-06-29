---
title: "var 的 hoisting：賦值（初始化）前使用不報錯"
tag: 
- 
---

##  var 的 hoisting：賦值（初始化）前使用不報錯
> 分為兩個步驟：
> - 宣告（hoisting）
> - 賦值（[初始化(initializer)](初始化(initializer).md)、不會 hoisting）

- 在 [Creation Phase](Creation%20Phase.md) 階段就該作用域開一個記憶體給 `var` 變數
- 賦值前使用只會跳 `undefined`，不會炸掉

> 為了程式碼穩定，你應該使用 `let`, `const` 並且希望他炸掉：[暫時性死區(TDZ)](暫時性死區(TDZ).md)

>長得有點像但不是：[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)

```javascript
console.log(a);	// 不會 not defined 炸掉，而是輸出 undefined 
var a = 1; 
console.log(a); // 輸出 1
```
hoisting 的效果可以解讀成
```javascript
var a; 			// hoisting（開個記憶體給 var a）
console.log(a);	// log undefined
var a = 1; 		// 賦值
console.log(a); // 輸出 1
```

