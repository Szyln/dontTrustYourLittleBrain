## function.call(obj, arguments)
>比較：[[置換函式的 this 指向]]

- 綁定 [this 的指向](this%20的指向.md)
- 不用丟到變數裡使用

```js
const obj1 = {
  objNumber: 1000,
}
// simple call: 原本的 this 指：window
function fn1(a, b, c) {
  console.log('bind', this, this.objNumber, a, b, c);

}

// call
fn1.call(obj1, '1', '2', '3')
```

