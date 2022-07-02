---
title: "function 被全域呼叫（simple call）"
tag: 
- 
---

##  function 被全域呼叫（simple call）
> 這並不常用，可以搭配[置換函式的 this 指向](置換函式的%20this%20指向.md)，來指定 this 是誰

function 在全域中，function 中的 this 指向全域
```js
var someone = '全域';
function callSomeone() {
  // 呼叫全域的變數：simple call
  console.log(this.someone);	// 指 global
}
callSomeone();
```