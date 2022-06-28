---
title: "function 被全域呼叫（simple call）"
tag: 
- 
---

##  function 被全域呼叫（simple call）
> 這並不常用

function 在全域中，function 中的 this 指向全域
```js
var someone = '全域';
function callSomeone() {
  // 呼叫全域的變數：simple call
  console.log(this.someone);	// 指 global
}
callSomeone();
```