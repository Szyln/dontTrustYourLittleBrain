---
title: "沒有被 function 包住的箭頭函式中的 this"
tag: 
- 
---

##  沒有被 function 包住的箭頭函式中的 this
沒有上層 function 那就是看全域
```js
var name = '全域'
const person = {
  name: '小明',
  callName: () => { 
    console.log(this.name); // 沒有外部 function 參考，this 會指向全域
  },
}
person.callName();
```