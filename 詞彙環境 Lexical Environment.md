## 詞彙環境 Lexical Environment
- 程式碼生成時的所在位置，代表他所在記憶體的位置
- 地址跟周遭有什麼都很重要

>不是執行時的位置：[執行環境 Execution Context](執行環境%20Execution%20Context.md)

```js
function fn() {
	var a = 'hi'	// a sits lexically inside the fn()
}
```