---
title: "Function Execution Context"
tag: 
- 
---

##  Function Execution Context
Function 被呼叫時的階段

### Creation Phase
- **不**生成 window object
- 生成 [[Scope 作用域]] （依照 [[範圍鏈 Scope Chaining]] 原則）
- 生成 this 
	- 指向看這個 function 是誰的屬性，都不是就是 [Window Object](Window%20Object.md) 的（[this 的指向](this%20的指向.md)）
	- [箭頭函式](箭頭函式.md) 不會生成
- [[Hoisting]]

>- this 的差異請參照：[this 的指向](this%20的指向.md)
>![](this%20的指向.md#^91e83b)

### Execution Phase
開始實際一行一行跑程式（按照 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)）