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
	- [傳值與傳參考](傳值與傳參考.md)
	- [改變 Mutate](改變%20Mutate.md)
	- [Array](Array.md)
	- [Function](Function.md)
		- [一級函式 First Class Functions](一級函式%20First%20Class%20Functions.md)
		- [函式表達式 function expression](函式表達式%20function%20expression.md)
			- [Inline Function Expression](Inline%20Function%20Expression.md)
		- [IIFE：宣告後直接執行函式](IIFE：宣告後直接執行函式.md)
		- [Arguments](Arguments.md)
			- [Spread Parameter](Spread%20Parameter.md)


### Framework
- [Function Overloading 重載函式](Function%20Overloading%20重載函式.md)
- [White space](White%20space.md)
- [用 IIFE 製作安全的程式碼](用%20IIFE%20製作安全的程式碼.md)


## 閉包 Closure
- `function`（稱 A） 的 `return` 是另一個 `function`（稱 B）
- A 得到 `return` 的時候，A 的 [Function Execution Context](Function%20Execution%20Context.md) 已經結束，從 Stack（[Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md)）中清除
	- 但 A 中 [Arguments](Arguments.md), 或是宣告都會保留在記憶體中，讓 return 始用
- B 開始執行他的 [Function Execution Context](Function%20Execution%20Context.md)
	- 遇到要從 A 拿的值，還是拿得到（Closure）

這種把已經結束的函式 (A) 的宣告，留在 `return` 的函式（B）可以讀取的範圍內的現象就稱為閉包 Closure

### 範例
```js
function greet(lines) {
	return function(name) {
		console.log(`${lines}, ${name}`)	
	}
}
// 可以這樣呼叫
greet('hi')('Amy')	// log hi, Amy
// 或是這樣寫
const sayHi = greet('hi')
sayHi('Amy')				// log hi, Amy
```
不是參數也可以
```js
function fn1(a) {
  let b = 'b'
  function fnInFn1() {
    console.log('fnInFn1 in fn1');
    
  }
  return function fn2(c) {
    console.log(a, b, c);   // 可以讀取
    fnInFn1()   						// 可以執行
  }
}
const fn3 = fn1('a')
fn3('c')			
// log a b c
// log fnn in fn1
```

## for
```js
function buildFn() {
  const arr = []
  // var 跟 let 會有不同效果請注意（跟嚴格模式無關）
  for (var i = 0; i < 3; i++) {
    arr.push(
      function () {
        console.log(i)
      }
    )
  }

  return arr
}
const buildedArr = buildFn()
buildedArr[0]()
buildedArr[1]()
buildedArr[2]()
// var: log 三次 3
// let: log 0, log 1, log 2
```