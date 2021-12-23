## 建置
- import：[[Express 匯入]]
- [[Middleware(express)]]
	- [[Express 的 CSS 樣式環境建置 (Serving a Static File)]]
- [[Request Handling(Express)]]
- port listening

> 之後再搭配 EJS 的話：[[EJS with Express 的基本設定]]
```js
// app.js
const express = require('express')
const app = express()

// middleware
app.use(express.static('public'));

// request handling(routing)
app.get('/', function (req, res) {	// 參數：網址，建立 server
	res.send('Hello World')			// 顯示文字
})

// port listening
app.listen(3000)					// 監聽 port
```
#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 