---
title: "JavaScript 全攻略：克服 JS 的奇怪部分（目錄）"
tag: 
- 
---

##  JavaScript 全攻略：克服 JS 的奇怪部分（目錄）

- Conceptual Aside：觀念小叮嚀
	- [執行環境 Execution Context](執行環境%20Execution%20Context.md)
	- [詞彙環境 Lexical Environment](詞彙環境%20Lexical%20Environment.md)
	- [語法解析器 Syntax Parsers](語法解析器%20Syntax%20Parsers.md)
	- [Key-Value Pair](Key-Value%20Pair.md)
	- [Object](Object.md)

## undefined
已宣告尚未指派，也是一個值

>當 `var` 變數被宣告時，一定有個值，預設是 `undefined`

```js
// var, let, const
var a;			// undefined
let b;			// undefined
const c;		// 禁止未賦值，炸掉
console.log(a)


```
```js
var a;
console.log(a)
var a = 1

// undefined 不會炸
```

