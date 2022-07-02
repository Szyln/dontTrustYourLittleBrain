### setTimeout 的 Closure
```js
function hiLater() {
	var greeting = 'Hi'
	setTimeout(function() {
		console.log(greeting)			// 取得 hiLater 的值（closure）
	}, 3000)
}

hiLater()
```