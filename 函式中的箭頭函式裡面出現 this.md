---
title: "函式中的箭頭函式裡面出現 this"
tag: 
- 
---

##  函式中的箭頭函式裡面出現 this
>[Function Execution Context](Function%20Execution%20Context.md) 不形成 this

箭頭函式內的 this 跟等同於**包住他的外層 function** 的 this

```js
var name = '全域'
const person = {
  name: '小明',
  callName: function () { 
    console.log('1', this.name); // 1 小明
    setTimeout (() => {
      console.log('2', this.name); // 2 跟外層的 this.name 一樣都是小明
      console.log('3', this); // 3 跟外層的 this 一樣都是 person
    }, 10);
  },
}
person.callName(); 
```