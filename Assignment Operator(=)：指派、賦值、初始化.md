---
title: "Assignment Operator(=)：指派、賦值、初始化"
tag: 
- 
---

##  Assignment Operator(=)：指派、賦值、初始化
[相依性 Associativity](相依性%20Associativity.md)：right-to-left

指派，右邊指派到左邊，不是==等於==


```js
var a = 1, b = 3, c = 4;
```
```js
a = b = c
console.log(a, b, c) // log 4 4 4 
```
```js
b = c
// return 4
```

>之後需要知道：
>- [變數 variables](變數%20variables.md)
>- [undefined](undefined.md)
>- [const](const.md)
>- [初始化(initializer)](初始化(initializer).md)