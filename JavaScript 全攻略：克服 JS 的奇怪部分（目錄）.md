---
title: "JavaScript 全攻略：克服 JS 的奇怪部分（目錄）"
tag: 
- 
---

##  JavaScript 全攻略：克服 JS 的奇怪部分（目錄）

- [語法解析器 Syntax Parsers](語法解析器%20Syntax%20Parsers.md)
- [Single-thread](Single-thread.md)
- [Scope 作用域](Scope%20作用域.md)
	- [範圍鏈 Scope Chaining](範圍鏈%20Scope%20Chaining.md)
	- [執行環境 Execution Context](執行環境%20Execution%20Context.md)
	- [詞彙環境 Lexical Environment](詞彙環境%20Lexical%20Environment.md)
		- [Variable Environment](Variable%20Environment.md)
	- [Invocation 呼叫函式](Invocation%20呼叫函式.md)
- [將變數定義預設值](將變數定義預設值.md)
- [複數 script 時的執行環境](複數%20script%20時的執行環境.md)


- [資料型別](資料型別.md)
	- [型別](型別.md)
	- [原始資料類型 Primitive Data Types](原始資料類型%20Primitive%20Data%20Types.md)
		- [undefined](undefined.md)
	- [Coercion 強迫](Coercion%20強迫.md)
	- [Object](Object.md)
		- [Key-Value Pair](Key-Value%20Pair.md)
	- [運算子 Operator](運算子%20Operator.md)
		- [優先性 Operator Precedence](優先性%20Operator%20Precedence.md)
		- [相依性 Associativity](相依性%20Associativity.md)


- Object
	- [用物件做 Name Space](用物件做%20Name%20Space.md)
	- 很像但不一樣的格式：[JSON](JSON.md)
	- [Function](Function.md)
		- [一級函式 First Class Functions](一級函式%20First%20Class%20Functions.md)
		- [函式表達式 function expression](函式表達式%20function%20expression.md)
			- [Inline Function Expression](Inline%20Function%20Expression.md)
	- [傳值與傳參考](傳值與傳參考.md)
	- [改變 Mutate](改變%20Mutate.md)
	- [Array](Array.md)

## Arguments
傳入函式中的參數，預設 `undefined`（與 [Hoisting](Hoisting.md) 有關）

```js
// 定義的時候叫 parameter
function fn1(parameters) {
	console.log(parameters)	
}
fn1(); // log undefined
// 導入的時候叫 argument
fn1(argument)
```

- [更改參數預設](更改參數預設.md)

### Arguments 也是屬性
不完全是一個陣列，但是一個類陣列
```js
function fn1(a, b, c) {
  console.log(a, b, c);
  console.log(arguments, typeof arguments);

}
fn1(2, 3, 5)
// log 2 3 5
// log 看圖
```

![](https://i.imgur.com/Lb98kRF.png)
### 應用
```js
function fn1(a, b, c) {
	if (arguments.length < 3) {
		console.log('缺少某個參數！')
		return
	} else if (arguments.length > 3) {
		console.log('參數多寫了！')
		return
	}
  console.log(a, b, c);
  console.log(arguments, typeof arguments);

}
fn1(2, 3, 5)
```
