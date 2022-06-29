---
title: "Global Execution Context"
aliases: <Base Execution Context>
tag: 
- js/executionContext
---
# Global Execution Context 全域執行環境
為 [Execution Phase](Execution%20Phase.md) 的其中一種，不管在程式碼的那個地方都可以讀取這裡的東西

## Creation Phase
- 生成 [Window Object](Window%20Object.md)
- 生成 [[Scope 作用域]] （依照 [[Closure(Scope Chaining)]] 閉包原則）
- 生成 [this](this.md) （指向 window）
- [[Hoisting]]

>- 在 Global 之下 [Window Object](Window%20Object.md) === [this](this.md)

>- this 的差異請參照：[this 的指向](this%20的指向.md)

## Execution Phase
開始實際一行一行跑程式（按照 [Call Stack（呼叫堆疊）](Call%20Stack（呼叫堆疊）.md)）

