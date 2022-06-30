## this 的指向
- [Global Execution Context](Global%20Execution%20Context.md)：指全域
- [Function Execution Context](Function%20Execution%20Context.md)：看 Function 的 
- [箭頭函式 arrow function](箭頭函式%20arrow%20function.md)：看上層的 function 的 this，沒有上層 function 就是 window

|           |Global| Function |箭頭 Function|
| --------- | ---- |-|-|
| this 指向 | window |看前面 `.` 誰（只有兩種情形，==不是看作用域==）<br>- 沒有對誰：[Window Object](Window%20Object.md)<br>- 對物件：物件<br>|- 沒有自己的 this<br>- 上層是 function： function 的 this<br>- 上層不是 function：window|

^91e83b

> - ==function 的 this 不會是 function==
> - [callback function：參數裡的 function 沒有在物件裡面](callback%20function：參數裡的%20function%20沒有在物件裡面.md)，指向 [Window Object](Window%20Object.md)
