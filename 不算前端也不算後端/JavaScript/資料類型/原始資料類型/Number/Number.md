---
title: "Number"
tag: 
- js/dataType/primitiveDataType 
---
# Number
- `NaN`: not a number
- `Infinity`: 無限大
- [Floating Point](Floating%20Point.md)：會帶有小數點導致一些運算上的誤差，可以用 [toFixed()：去除小數點後第幾位](toFixed()：去除小數點後第幾位.md) 解決這個問題

```js
console.log(5 / 0); // log Infinity
console.log(Infinity / Infinity); // log Infinity 跟微積分有關（好）
NaN === NaN; // log false 想要認定是否為 NaN 要用 isNaN
```

>[運算子 Operator](運算子%20Operator.md)

