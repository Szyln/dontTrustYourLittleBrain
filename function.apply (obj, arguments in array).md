## function.apply (obj, arguments in array)
>比較：[[置換函式的 this 指向]]

- 綁定 [this 的指向](this%20的指向.md)
- 不用丟到變數裡使用
- 函式的 [Arguments](Arguments.md) 必須放在陣列裡
- 陣列可以做的處理比較多，需要複雜的功能的時候建議用 `apply`

```js
const obj1 = {
  objNumber: 1000,
}
// simple call: 原本的 this 指：window
function fn1(a, b, c) {
  console.log('bind', this, this.objNumber, a, b, c);

}

/// apply
fn1.apply(obj1, ['1', '2', '3'])
```
