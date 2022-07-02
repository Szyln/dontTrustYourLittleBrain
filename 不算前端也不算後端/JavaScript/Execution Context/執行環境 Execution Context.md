---
title: "執行環境 Execution Context"
aliases: <執行脈絡>,<執行上下文>
tag: 
- js/executionContext
---
## 執行環境 Execution Context
當程式碼「執行」時，按照 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)，經歷兩個階段
- 背景運作：[Creation Phase](Creation%20Phase.md)
- 實際運作：[Execution Phase](Execution%20Phase.md)：當中又有呼叫 function 時，就會進行該 function 的 [執行環境 Execution Context](執行環境%20Execution%20Context.md)（就算是跟目前同一個 function 也會）

> 程式碼的
> - 執行：被 [執行環境 Execution Context](執行環境%20Execution%20Context.md) 管理
> - 生成：被 [詞彙環境 Lexical Environment](詞彙環境%20Lexical%20Environment.md) 管理


### Phase 階段
- [[Creation Phase]]
- [[Execution Phase]]


### 類型
- [[Global Execution Context]]（會生成 window object）
- [[Function Execution Context]] (不會生成 window object) 



| Execution Context 執行環境 \ Phase 階段 | Creation                                                                                                                                                                          | Execution                                                  |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Global                                  | - 生成 [Window Object](Window%20Object.md) <br>- 生成 [Scope 作用域](Scope%20作用域.md)<br> - 生成 [this](this.md) (指向 [Window Object](Window%20Object.md)) <br>- [Hoisting](Hoisting.md)       | - 按照 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)<br>- 如果遇到[Invocation 呼叫函式](Invocation%20呼叫函式.md) 則開啟該 function 的 [Function Execution Context](Function%20Execution%20Context.md) |
| Function                                | - 生成 [Scope 作用域](Scope%20作用域.md)<br>- 生成 [this](this.md)（==除了[箭頭函式](箭頭函式.md)==）<br>- [Hoisting](Hoisting.md) | - 按照 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)<br>- 如果遇到[Invocation 呼叫函式](Invocation%20呼叫函式.md) 則開啟該 function 的 [Function Execution Context](Function%20Execution%20Context.md) |

^17ae59

### Global & Function 的 this 差別
![](this%20的指向.md#^91e83b)