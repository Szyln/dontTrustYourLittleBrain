---
title: "置換函式的 this 指向"
tag: 
- js/function
---
## 置換函式的 this 指向
>[箭頭函式](箭頭函式.md) 沒有 [this](this.md) 並不適用這些 method

傳統的 function （當成物件在使用）都可以執行的 method
- [function.bind(obj)](function.bind(obj).md)
- [function.call(obj, arguments)](function.call(obj,%20arguments).md)
- [function.apply (obj, arguments in array)](function.apply%20(obj,%20arguments%20in%20array).md)
- vue: [vue 置換 this 指向](vue%20置換%20this%20指向.md)
- [用 IIFE 精簡置換 this 指向的步驟](用%20IIFE%20精簡置換%20this%20指向的步驟.md)

|                    | bind | call | apply |
| ------------------ | ---- | ---- | ----- |
| 函式可以帶入參數   | 是   | 是   | 是    |
| 需要存到新的變數中 | 是（copy 這個 function）   | 否   | 否    |
| 帶入參數要用陣列   | 否   | 否   | 是    |

```js
const obj1 = {
  objNumber: 1000,
}
// simple call: 原本的 this 指：window
function fn1(a, b, c) {
  console.log('bind', this, this.objNumber, a, b, c);

}

// bind 需要寫比較多
const fn2 = fn1.bind(obj1);
fn2('1', '2', '3')
// call
fn1.call(obj1, '1', '2', '3')
/// apply
fn1.apply(obj1, ['1', '2', '3'])
```
