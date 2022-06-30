---
title: "let"
tag: 
- 
---

##  let

>- [Scope 作用域](Scope%20作用域.md)
>- [暫時性死區(TDZ)](暫時性死區(TDZ).md)
>- [執行環境 Execution Context](執行環境%20Execution%20Context.md)
>- [undefined](undefined.md)


 | 外層作用域宣告 | 當前作用域宣告 | 同作用域有沒有使用後宣告 |       結果       |
 | :------------: | :------------: | :----------------------: | :--------------: |
 |      任意      |      任意      |            O             |       TDZ 炸        |
 |      任意      |       O        |            X             | 看當前作用域宣告（預設值 `undefined`） |
 |       O        |       X        |            X             | 看外層作用域宣告（預設值 `undefined`）|
 |       X        |       X        |            X             |  not define 炸   |

^8b4b01
