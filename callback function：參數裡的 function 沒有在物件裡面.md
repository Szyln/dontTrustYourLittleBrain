---
title: "callback function：參數裡的 function 沒有在物件裡面"
tag: 
- js/function
---

##  callback function：參數裡的 function 沒有在物件裡面

- 物件中的 function(this 為物件) 內部
	- 呼叫有 callback function 的 function
	- callback function 不是 [箭頭函式 arrow function](箭頭函式%20arrow%20function.md) 的話，生成的 this 指向 [Window Object](Window%20Object.md)


```js
let a = 1
var obj = {
  a: 2,
  fn: function() {
		console.log(this); 						// obj
    setTimeout(function () {
      console.log(this.someone);    // callback: simple call
    });
  }
}
obj.fn();
```