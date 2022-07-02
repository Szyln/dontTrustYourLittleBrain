## function.bind(obj)
>比較：[[置換函式的 this 指向]]

- 綁定 [this 的指向](this%20的指向.md)
- 需要把 bind 過的內容丟到一個新的變數內使用

```js
const obj1 = {
  objNumber: 1000,
}

function fn1(a, b, c) {
  console.log('bind', this, this.objNumber, a, b, c);

}

// bind 需要寫比較多
const fn2 = fn1.bind(obj1);
fn2('1', '2', '3')
```
