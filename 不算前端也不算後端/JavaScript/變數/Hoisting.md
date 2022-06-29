---
title: "Hoisting"
tag: 
- js/variable/scope
---
## 提昇 Hoisting
>相反的概念是 [暫時性死區(TDZ)](暫時性死區(TDZ).md)

提升到**該 [Scope 作用域](Scope%20作用域.md)** 的頂部
- [function 的 hoisting](function%20的%20hoisting.md)
- [var 的 hoisting：賦值（初始化）前就可以用](var%20的%20hoisting：賦值（初始化）前就可以用.md)

> - let, const（[暫時性死區(TDZ)](暫時性死區(TDZ).md)）, function expression 不會 hoisting
> - `var` 的 hoisting 只有宣告本身，不包含值


### 不會 hoisting 的部分(lexical declaration)
- [但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)
- [暫時性死區(TDZ)](暫時性死區(TDZ).md)：
	- `let`
	- `const`




### 補充
- 發生的時間點 [執行環境 Execution Context](執行環境%20Execution%20Context.md) 的 [Creation Phase](Creation%20Phase.md)
- 電腦記憶體會先分配給 `function`, `var` 的宣告（lexical declaration: let, const, function expression 沒有），之後才會開始跑程式碼

