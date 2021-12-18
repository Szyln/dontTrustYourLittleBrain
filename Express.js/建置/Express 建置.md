## Express 建置
- import：[[Express 匯入]]
- middleware：[[Serving a Static File 回應有樣式的 HTML 檔案]]
- [[Request Handling(Express)]]
- port listening
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