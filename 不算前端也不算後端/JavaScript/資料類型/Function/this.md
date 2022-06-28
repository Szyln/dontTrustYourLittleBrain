---
title: "this"
tag: 
- 
---
# this

## 目錄
- [function 被全域呼叫（simple call）](function%20被全域呼叫（simple%20call）.md)
- [function 被 object 呼叫](function%20被%20object%20呼叫.md)
- [不同物件呼叫了同名的函式](不同物件呼叫了同名的函式.md)

### 陷阱題
- object 中還有 object
- Object 裡面的 function 硬要呼叫全域 function
- callback function


## 特性
- this 是[[函式的隱藏的參數]]之一
- 指向會變動
-  ** function 是從哪裡宣告的，就是指誰**（ES6 的 this 參照[[箭頭函式 arrow function]]）
- 主流框架都會用到

- [this 的指向](this%20的指向.md)




### 陷阱題

#### Object 中還有 Object

```js
var wrapObj = {
  someone: '外層物件',
  callSomeone(),          // wrapObj 的 function
  innerObj: {
    someone: '內層物件',
    callSomeone(),        // innerObj 的 function
  }
}
wrapObj.innerObj.callSomeone();
```

#### Object 裡面的 function 硬要呼叫全域 function

callSomeone 還是全域的 funciton

```js
var obj3 = {
  someone: '物件 3',
  fn() {
    callSomeone(); // 通常平常不會這樣去取用 this
  }
}
obj3.fn();
```

#### callback function：避免用

使用 callback function（像是在forEach裡），大部分就是把一個定義好的 function 簡化放到 callback funciton 裡面
所以他還是一個全域的 function

```js
var obj4 = {
  someone: '物件 4',
  fn() {
    setTimeout(function () {
      console.log(this.someone);    // simple call
    });
  }
}
obj4.fn();
```


#js #vue #advanceJs