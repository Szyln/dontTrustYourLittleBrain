---
title: "Logic AND(&&)"
tag: 
- js/logic
---
## Logic AND(&&)
>[mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)

```js
expr1 && expr2
```
如果 expr1 是真值，傳 expr1，其餘傳 expr2
- expr1 為真值 --> 如果 expr2 也是真值回傳 expr2
- 一碰到偽值就回傳

```js
// 偽 && 真
result = '' && 'foo';  // result is assigned "" (empty string)
// 真 && 偽
result = 2 && 0;       // result is assigned 0

result = 'foo' && 4;   // result is assigned 4
```