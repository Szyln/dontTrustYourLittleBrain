## 閉包 Closure
- `function`（稱 A） 中有另一個 `function`（稱 B）需要取得 A 的宣告
- A 得到 `return` 的時候，A 的 [Function Execution Context](Function%20Execution%20Context.md) 已經結束，從 Stack（[Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)）中清除
	- 但 A 中 [Arguments](Arguments.md), 或是宣告都會保留在記憶體中
- B 開始執行他的 [Function Execution Context](Function%20Execution%20Context.md)
	- 遇到要從 A 拿的值，還是拿得到（Closure）

這種把已經結束的函式 (A) 的宣告，還會在函式中的函式（B）可以讀取的範圍內的現象就稱為閉包 Closure

### 範例
只要函式裡面有函式，而且要讀到外面函式的值，就是閉包
- [return function 的 closure](return%20function%20的%20closure.md)
- [for 迴圈的 Closure](for%20迴圈的%20Closure.md)
- [Function Factories](Function%20Factories.md)
- [setTimeout 的 Closure](setTimeout%20的%20Closure.md)