---
title: "原始資料類型使用 Prototype Inheritance 的功能"
tag: 
- js/object/oop
- js/dataType/primitiveDataType 
---
# 原始資料類型使用 Prototype Inheritance 的功能
## Coercion
JS 屬於 
[原始資料類型 Primitive Data Types](原始資料類型%20Primitive%20Data%20Types.md) 沒有自己的 methods，但因為 JS 有 Coercion 的特性，就算不是物件，也可以使用物件繼承來的功能。 
## 示範
[Primitive Coercion 將原始資料類型強制改成物件來用](Primitive%20Coercion%20將原始資料類型強制改成物件來用.md)

不推薦：可以透過 [[Constructor]] 的方法去做[不正常的作法](Primitive%20Coercion%20將原始資料類型強制改成物件來用.md#不正常的作法)物件類型的 string
推薦：利用 Coercion 的特性，讓原始資料類型讀取 prototype


