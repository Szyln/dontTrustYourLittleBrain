---
title: "Execution Context"
tag: 
- js/executionContext
---
# Execution Context

## Phase 階段
- [[Creation Phase]]
- [[Execution Phase]]

## 類型
- [[Global Execution Context]]（會生成 window object）
- [[Function Execution Context]] (不會生成 window object) 


| Execution Context 執行環境 \ Phase 階段 | Creation                                                                                                                                                                          | Execution                                                  |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Global                                  | - 生成 [Window Object](Window%20Object.md) <br>- 生成 [Scope 作用域](Scope%20作用域.md)<br> - 生成 [this](this.md) (指向 [Window Object](Window%20Object.md)) <br>- [Hoisting](Hoisting.md)       | 按照 [Call Stack（呼叫堆疊）](Call%20Stack（呼叫堆疊）.md) |
| Function                                | - 生成 [Scope 作用域](Scope%20作用域.md)<br>- 生成 [this](this.md)（==除了[箭頭函式 arrow function](箭頭函式%20arrow%20function.md)==，指向看 [this](this.md) 這篇）<br>- [Hoisting](Hoisting.md) | 按照 [Call Stack（呼叫堆疊）](Call%20Stack（呼叫堆疊）.md) |

^17ae59

### Global & Function 的 this 差別
![](this%20的指向.md#^91e83b)