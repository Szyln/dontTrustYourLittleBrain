## String Concatenate （串接）
> 串接 concatenate 簡稱 concat

```js
let str = `hi` + ", I am fine."
```

- string 可以做串接（`+`），但不能做運算（加減乘除）
- `string` 可以串接 `number`，會當成 `string` ^577182

> 但在 python 可以做乘法

### string number concatenate（串接）
字串可以串接數字，但數字不可串接數字

| 兩個資料類型    | `+` 所執行的動作 |
| --------------- | -------- |
| string + 任意   | 串接     |
| number + number | 運算     |

```js
1 + 100 + "1000" + 3 + 6
// 答案是：101100036

// 運算順序是左到右
// "1001000" + 3 + 6
// "10010003" + 6
```