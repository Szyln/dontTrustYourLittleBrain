# Node to API
[[Fetch#需要有 Authorization Key 才能使用的 API]]
>Node 是不支援 [[Fetch]] 功能的
## 步驟
### 終端
```
npm init
npm install express ejs nodemon 
(不用安裝 mongoose)
```
### 匯入
```js
// app.js
const express = require('express');
const app = express();
const ejs - require('ejs');
```
>[[Express.js]]
>[[EJS]]
### api 資料
```js
// api key 
const key = 'api 提供的金鑰' ;
```

### [[Middleware(express)]]
[[app.set()]]
```js
// middleware
app.use(express.static('public'));
// 這是啥
app.set('view engine', 'ejs');
```
### [[Routing]]
```js
// request handdling
app.get('/', (req, res) => {
	res.render('index.ejs')
})

app.get('/:city', (req, res) => {
	let { city } = req.params;
	let url = `API 給的 endpoint`
	
	// get request made by node.js
	https.get('url', (response) => {
		console.log('statusCode:', response.statusCode);
		console.log('headers:', response.headers); 
		
		response.on('data', (d) => {
			// string to array
			let dJson = JSON.parse(d);
			console.log(dJson);
			res.render('weather.ejs', { dJson });
		});

		}).on('error', (e) => {
			console.error(e);
		});
	
	

})
```
>- [[從物件中提取屬性到變數中 Destructing an object]]
>- [[類型轉換#JSON]] JSON.parse(string)：轉成 array
>- [[EJS#在 HTML 內使用變數：Routing for pattern]]
> [[Node to API - 使用 fetch 的狀況（不支援）]]
### 使用 API
[[Fetch]] 是不支援的
#### [https.get](https://nodejs.org/docs/latest-v15.x/api/https.html#https_https_get_options_callback)

### listen
```js
app.listen(3000, () => {
	console.log('server is running on 3000')
})
```
