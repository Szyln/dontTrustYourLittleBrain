## this 的指向
- [Global Execution Context](Global%20Execution%20Context.md)：指全域
- [Function Execution Context](Function%20Execution%20Context.md)：看 Function 的是誰的屬性
- [箭頭函式 arrow function](箭頭函式%20arrow%20function.md)：看上層的 function 的 this，沒有上層 function 就是 window

|           |Global| Function |箭頭 Function|
| --------- | ---- |-|-|
| this 指向 | window |看是誰的屬性（只有兩種情形，==不是看作用域==）<br>- 沒有誰：[Window Object](Window%20Object.md)<br>- 物件的：物件<br>|- 沒有自己的 this<br>- [詞彙環境 Lexical Environment](詞彙環境%20Lexical%20Environment.md) 是 function： 該 function 的 this<br> / 不是：window|

^91e83b

> - ==function 的 this 不會是 function==
> - [callback function：參數裡的 function 沒有在物件裡面](callback%20function：參數裡的%20function%20沒有在物件裡面.md)，指向 [Window Object](Window%20Object.md)
