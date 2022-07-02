## 閉包 Closure
- `function`（稱 A） 的 `return` 是另一個 `function`（稱 B）
- A 得到 `return` 的時候，A 的 [Function Execution Context](Function%20Execution%20Context.md) 已經結束，從 Stack（[Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)）中清除
	- 但 A 中 [Arguments](Arguments.md), 或是宣告都會保留在記憶體中，讓 return 始用
- B 開始執行他的 [Function Execution Context](Function%20Execution%20Context.md)
	- 遇到要從 A 拿的值，還是拿得到（Closure）

這種把已經結束的函式 (A) 的宣告，留在 `return` 的函式（B）可以讀取的範圍內的現象就稱為閉包 Closure

### 範例
- [return function 的 closure](return%20function%20的%20closure.md)
- [for 迴圈的 Closure](for%20迴圈的%20Closure.md)