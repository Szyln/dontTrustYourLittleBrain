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
- 第一個碰到的偽值
- 兩者皆為真值，回傳 expr2
```js
// 偽 && 真
result = '' && 'foo';  // 回傳偽值
// 真 && 偽
result = 2 && 0;       // 回傳偽值
// 真 && 真
result = 'foo' && 4;   // 回傳 expr2
```

>[Falsy Value](Falsy%20Value.md)