---
title: "JavaScript 全攻略：克服 JS 的奇怪部分（目錄）"
tag: 
- 
---

##  JavaScript 全攻略：克服 JS 的奇怪部分（目錄）


- [執行環境 Execution Context](執行環境%20Execution%20Context.md)
- [詞彙環境 Lexical Environment](詞彙環境%20Lexical%20Environment.md)
- [語法解析器 Syntax Parsers](語法解析器%20Syntax%20Parsers.md)
- [Key-Value Pair](Key-Value%20Pair.md)
- [Object](Object.md)
- [undefined](undefined.md)
- [Single-thread](Single-thread.md)

## Invocation 呼叫函數
```js
function fn() {
	console.log('invocated!')
}

// 這就是 Invocation
fn()
```

```js
function fn1() {
	fn2()
}

function fn2() {
	console.log('fn2 is invocated!')
}

fn1() // invocated fn1
```

## stack
當程式碼「執行」時，按照 [Call Stack 呼叫堆疊](Call%20Stack%20呼叫堆疊.md) 的規則，會產生兩種 [執行環境 Execution Context](執行環境%20Execution%20Context.md)
```mermaid
graph BT
A(生成 Global Execution Context) --> B[fn1 生成 Function Execution Context]
B --> C[fn2 生成 Function Execution Context]
C --> B
```
