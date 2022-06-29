---
title: "Hoisting"
tag: 
- js/variable/scope
---
## 提昇 Hoisting
>相反的概念是 [暫時性死區(TDZ)](暫時性死區(TDZ).md)

在 [Creation Phase](Creation%20Phase.md) 階段就該作用域開一個記憶體給
- [var 的 hoisting：賦值（初始化）前使用不報錯](var%20的%20hoisting：賦值（初始化）前使用不報錯.md)
- [function 的 hoisting](function%20的%20hoisting.md)

導致 [Execution Phase](Execution%20Phase.md) 的時候隨時都可以讀到 `var`（值未定義，`undefined`） , `function`（可以使用）


> - let, const（[暫時性死區(TDZ)](暫時性死區(TDZ).md)）, function expression 不會 hoisting


### 不會 hoisting 的部分(lexical declaration)
- [但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)
- [暫時性死區(TDZ)](暫時性死區(TDZ).md)：
	- `let`
	- `const`




### 補充
- 發生的時間點 [執行環境 Execution Context](執行環境%20Execution%20Context.md) 的 [Creation Phase](Creation%20Phase.md)
- 電腦記憶體會先分配給 `function`, `var` 的宣告（lexical declaration: let, const, function expression 沒有），之後才會開始跑程式碼

