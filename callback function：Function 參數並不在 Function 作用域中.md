---
title: "callback function：Function 參數並不在 Function 作用域中"
tag: 
- js/function
---

##  callback function：Function 參數並不在 Function 作用域中
>[Function Execution Context](Function%20Execution%20Context.md) 的作用域是在 `{}` 中間，不包括參數

使用 callback function（像是在 forEach 裡），大部分就是把一個定義好的 function 簡化放到 callback function 裡面
所以他還是一個全域的 function

```js
let a = 1
var obj = {
  a: 2,
  fn: function() {
		console.log(this) 						// obj
    setTimeout(function () {
      console.log(this.someone);    // simple call
    });
  }
}
obj.fn();
```