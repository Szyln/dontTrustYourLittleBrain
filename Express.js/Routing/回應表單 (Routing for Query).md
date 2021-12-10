# 回應表單 (Routing for Query)
回應取代一般的 get ，會使用對應 [[form]] 的 post 功能
## POST([[form]])
```html
// index.html

// action: 資料傳送目的地
// POST: 不會顯示在網址
<form action="/formHandling" method="POST">

	// 有 name 屬性的 input 才會送到 form action 的所在地
	<label for="name">Your Name</label>
	<input type="text" id="name" name="name">

	<label for="age">Your Age</label>
	<input type="text" id="age" name="age">
	
	<input type="submit">Submit</input>

</form>
```

```js

// 回應上面的這個 index.html 檔
app.get('/', (req, res) => {
	res.sendFile(path.join(__dirname, "index.html"))
})

// 對方送出表單後的回應
app.post('/formHandling', (req, res)) {
	console.log(req.body);
	res.send("表單已送出");
}
```

>[[Module Wrapper#__dirname#使用方式]]：有兩種作法，單純使用[[string#string 的串接]]或是使用 path 模組 + [[join()]]


### req.body
想要細部使用表單內容需要先處理的步驟
```js
const bodyParser = require("body-parser");

// middleware 收到請求一定會被執行
app.use(bodyParser.urlencoded(
	{ extended: true }
)});
```
```js
// 這裡就可以使用 body 的內容了
app.post('/formHandling', (req, res)) {
	let { name, age } = req.body	// body 為表單資訊
	res.send(已經送出，您的名字是 ${name} 年齡 ${age} 歲`);
	
}
```
> 很像物件的變數：[[從物件中提取屬性到變數中 Destructing an object]]
> 學到 [[Database 數據庫]]之後會有更複雜的應用（資料先傳到資料庫再傳回來）
## GET([[form]])
跟一般的請求回應一樣都是使用 `.get()` 來回應對方的表單
```html
// index.html

// action: 資料傳送目的地
// GET: 會顯示在網址
<form action="/formHandling" method="GET">

	// 有 name 屬性的 input 才會送到 form action 的所在地
	<label for="name">Your Name</label>
	<input type="text" id="name" name="name">

	<label for="age">Your Age</label>
	<input type="text" id="age" name="age">
	
	<input type="submit">Submit</input>

</form>
```

```js
// 回應上面的這個 index.html 檔

// 不需要 middileware, bodyParser

app.get('/', (req, res) => {
	res.sendFile(path.join(__dirname, "index.html"))
})

// GET 的表單會更改網址
// 對方送出表單後的回應
app.get('/formHandling', (req, res)) {
	let { name, age } = req.query	// query 可以 get 的讀取表單資訊
	res.send(已經送出，您的名字是 ${name} 年齡 ${age} 歲`);
}
```

#js #expressJs #node #npm #form #server #routing