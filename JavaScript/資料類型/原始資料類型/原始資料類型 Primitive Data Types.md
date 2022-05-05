---
title: "原始資料類型 Primitive Data Types"
tag: 
- js/dataType/primitiveDataType 
---
# 原始[資料類型 index](JavaScript/資料類型/資料類型%20index.md) primitive data types
**不是物件**，沒有自己的屬性與功能
擁有自己的值，不是參考

>[Primitive Coercion 將原始資料類型強制改成物件來用](JavaScript/資料類型/資料類型/Primitive%20Coercion%20將原始資料類型強制改成物件來用.md)

- [Number](JavaScript/資料類型/原始資料類型/Number/Number.md)
- [string](JavaScript/資料類型/原始資料類型/string.md)
- [Boolean](JavaScript/資料類型/原始資料類型/Boolean.md)
- symbol

### [傳值 Call By Value](物件傳參考#傳值%20Call%20By%20Value)
>進階概念，需要理解 [Object](JavaScript/資料類型/Object,%20Array/Object.md)、[物件的傳參考特性](JavaScript/資料類型/Object,%20Array/Object/物件的傳參考特性.md)

如果複製了一個原始資料類型，更改其中一個，不會影響到另一個

```js
let n1 = 100;
let n2 = n1;

n1 = 1;
console.log(n1, n2); // 傳值的特性 log 1 100
```
