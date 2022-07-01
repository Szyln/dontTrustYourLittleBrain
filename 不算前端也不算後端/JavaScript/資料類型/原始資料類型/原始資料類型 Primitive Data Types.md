---
title: "原始資料類型 Primitive Data Types"
tag: 
- js/dataType/primitiveDataType 
---
## 原始[資料型別](資料型別.md) primitive data types
- **不是物件**，沒有自己的屬性與功能
- 值，不是參考

>[Coercion 強迫](Coercion%20強迫.md)


### [傳值 Call By Value](物件傳參考.md#傳值%20Call%20By%20Value)
>進階概念，需要理解 [Object](Object.md)、[物件的傳參考特性](物件的傳參考特性.md)

如果複製了一個原始資料類型，更改其中一個，不會影響到另一個

```js
let n1 = 100;
let n2 = n1;

n1 = 1;
console.log(n1, n2); // 傳值的特性 log 1 100
```

![](資料型別.md#^28bc34)