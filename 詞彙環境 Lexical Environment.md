## 詞彙環境 Lexical Environment
>TODO：跟[Scope 作用域](Scope%20作用域.md)的差別

- 程式碼撰寫時的所在位置，代表==他所在記憶體的位置==


>地址 (Lexical Environment) 跟周遭（這個記憶體中的內容）有什麼都很重要

>不是執行時的位置：[執行環境 Execution Context](執行環境%20Execution%20Context.md)

```js
function fn() {
	var a = 'hi'	// a sits lexically inside the fn()
}
```