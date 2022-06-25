## return
### function 停止運作的時機
 function 遇到
 - `}`：function 會自己形成一個 [Scope](JavaScript/變數/Scope.md)（參照 function scope），`{}` 內的程式碼執行完後便會停止
 - `return`：回傳一個數值，結束這個 function 運作，不論後續還有沒有其他程式碼在 function 內

>```js
>function fun(x) {
>	return;
>}
>```
>不回傳東西當做終止 function 用

### return 跟 console.log 的差別
- `return` 是 `function` 回傳的結果，可以存到一個變數之中做使用
- `console.log` 只會將數值 print 到 console 裡面可以做檢視，並不會影響程式碼，[Debug and Lint](Debug%20and%20Lint.md)好用