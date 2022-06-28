---
title: "block"
tag: 
- js/variable/scope
---
## block (javascript)
>- [block(javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)
>- [[Scope 作用域]] 的其中一種
>- [Closure(Scope Chaining)](Closure(Scope%20Chaining).md)

```javascript
{
	陳述_1
	陳述_2
	...
	陳述_n
}
```
- 用大括號包起來
- 可以有 label（選用）：[Labeled Block Statement(optional)](Labeled%20Block%20Statement(optional).md)
- 常在 if else, for 時使用：[if, switch](if,%20switch.md), [for](for.md)




### [[Scope 作用域]]判定
非嚴格模式中很容易出現[全域污染](全域污染.md)的狀況

| block 內宣告會不會全域污染 |  var   |  let  | const | function |
| -------------------------- | :----: | :---: | :---: | :------: |
| 嚴格模式                   |   否   |  否   |  否   |    否    |
| 非嚴格模式                 | ==會== |  否   |  否   |  ==會==  |

- [非嚴格模式的 block](非嚴格模式的%20block.md)
- [嚴格模式的 block](嚴格模式的%20block.md)
