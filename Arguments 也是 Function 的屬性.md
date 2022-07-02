### Arguments 也是屬性
>建議用 [Spread Parameter](Spread%20Parameter.md) 取代

- 類陣列
- 可以作一些應用，但比較建議用：[Spread Parameter](Spread%20Parameter.md)

```js
function fn1(a, b, c) {
  console.log(a, b, c);
  console.log(arguments, typeof arguments);

}
fn1(2, 3, 5)
// log 2 3 5
// log 看圖
```

![](https://i.imgur.com/Lb98kRF.png)

### 應用
Arguments 是類陣列，可以用一些基本的陣列功能

>但現今建議用：[Spread Parameter](Spread%20Parameter.md)
- `.length`
- `arguments[index]`
- 等
```js
function fn1(a, b, c) {
	if (arguments.length < 3) {
		console.log('缺少某個參數！')
		return
	} else if (arguments.length > 3) {
		console.log('參數多寫了！')
		return
	}
  console.log(a, b, c);
  console.log(arguments, typeof arguments);

}
fn1(2, 3, 5)
```
