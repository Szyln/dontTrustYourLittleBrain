## 詞彙環境 Lexical Environment
>TODO：跟[Scope 作用域](Scope%20作用域.md)的差別

程式碼==他所在記憶體的位置==


>不是在說在程式碼的第幾行，是在說在哪個 [Scope 作用域](Scope%20作用域.md) 中

>不是執行時的位置：[執行環境 Execution Context](執行環境%20Execution%20Context.md)

```js
function fn() {
	var a = 'hi'	// a sits lexically inside the fn()
}
```