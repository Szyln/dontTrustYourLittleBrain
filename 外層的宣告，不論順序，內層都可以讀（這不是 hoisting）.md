## 外層的宣告，不論順序，內層都可以讀（這不是 hoisting）
外層（作用域）的宣告，不論順序，內層（作用域）都可以讀（這不是 hoisting）
```js
// // const c = 1 // 1
// // let c = 1   // 1
// // var c = 1   // 1
// // let c       // undefined
// // var c       // undefined
function fn() {
  console.log(c)
}
// // const c = 1 // 1
// // let c = 1   // 1
// // var c = 1   // 1
// // let c       // undefined
// // var c       // undefined

fn()
```