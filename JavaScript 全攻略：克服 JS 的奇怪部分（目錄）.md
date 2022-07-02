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

## 一級函式 First Class Functions
對其他[資料型別](資料型別.md)做的事，都可以對 [Function](Function.md) 做
- 指派給變數：[函式表達式 function expression](函式表達式%20function%20expression.md)
- 當 Function 的參數：[Callback Function](Callback%20Function.md)
- 像物件一樣新增屬性、方法

### 只有 function 型別有的
```js
// name 是一個 function 的屬性
function name(param) {
	// 這裡的 code 也是 function 的屬性
	// code here
	console.log(param)
}
```

- Function 的物件屬性
	- name(optional)
	- code（可以拿來 [Invocation 呼叫函式](Invocation%20呼叫函式.md)）

> 也有其他語言有這個功能，但 JS 中最活躍
