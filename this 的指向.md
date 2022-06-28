## this 的指向
- [Global Execution Context](Global%20Execution%20Context.md)：指全域
- [Function Execution Context](Function%20Execution%20Context.md)：看 Function 從哪呼叫
- [箭頭函式 arrow function](箭頭函式%20arrow%20function.md)：看上層的 function 的 this，沒有上層 function 就是 window

|           |Global| Function | 物件的 Function |箭頭 Function|
| --------- | ---- |-| ---------- |-|
| this 指向 | window |看誰呼叫的（兩種情形）<br>- 在 Global：window<br>- 在 Object：物件<br>- function 不能呼叫 function| 物件呼叫的，物件       |- 沒有自己的 this<br>- 上層是 function： function 的 this<br>- 上層不是 function：window|

^91e83b

> - ==function 無法呼叫 function==
> - [callback function：Function 參數並不在 Function 作用域中](callback%20function：Function%20參數並不在%20Function%20作用域中.md)：放在參數內的 function 是在 Global 呼叫的（並不存在於 [Function Execution Context](Function%20Execution%20Context.md) 中）
