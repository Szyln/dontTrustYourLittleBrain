---
title: "傳參考 By Reference"
aliases: reference data types,
tag: 
- 
---

##  傳參考 By Reference
>[參考](參考.md)
>
- 把記憶位置傳到另一個物件的記憶體位置上，為 link 非 copy
- JS 中物件型別是這個特性
- 彼此有 link 關係，所以在哪裡其中一方被修改了，兩邊都會更新

```js
const person = {
  name: '小明',
  obj: {}
}
cosnt person2 = person	// link
person2.name = '小王'		 // person 也會更新
```