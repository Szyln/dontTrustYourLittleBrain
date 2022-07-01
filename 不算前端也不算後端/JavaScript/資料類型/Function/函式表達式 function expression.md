---
title: "函式表達式 function expression"
tag: 
- 
---
# 函式表達式 function expression 
將函式儲存進一個變數中

>[但 function expression 不會 hoisting](但%20function%20expression%20不會%20hoisting.md)

## 語法
### 匿名函式
```js
const fnA = function(parameter) {
	// blabla
}
```
### 有名稱的函式 
```js
const fnB = function fnA(parameter) {
	// blabla
}
```
## 執行
```js
// 有參數的要放 argument
fnA()
```

>- [Callback Function](Callback%20Function.md)
>- [Inline Function Expression](Inline%20Function%20Expression.md)

#js #function