- ## Spread Parameter：陣列型別 Arguments，可以擴張的參數
當 function 想要使用 [Arguments](Arguments.md) 做一些處理的時候，建議使用這個功能，因為陣列可以做比較多事
```js
// ...other 是一個 array，名稱為 other(自訂)
function fn2(a, b, c, ...other) {
	console.log(other)
}
// 第四個開始的參數會直接存到一個 array 當中
fn2(1, 2, 4, 56, 22, 16)
// log 看圖
```

![](https://i.imgur.com/hQeYRbI.png)
