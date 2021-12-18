# Express.js
- 是 [[npm]] 中的一個模組
- Node.js 的一種框架（[[Library 跟 Framework 的差別]]），有助加速 Node.js 撰寫
- [[Routing]]
- 搭配 [[EJS]]

## 建置
- import
- middleware
- reqest handling
- port listening
```js
// app.js
const express = require('express')
const app = express()

app.get('/', function (req, res) {	// 參數：網址，建立 server
	res.send('Hello World')			// 顯示文字
})

app.listen(3000)					// 監聽 port
```


### [[匯入模組]]
頭兩行可以發現 `app` 這個變數直接將匯入的檔案當做函數處理
```js
// app.js
const express = require('express')
const app = express()
```
#### Express.js 的匯出方式（不用自己做）
以往我們是將檔案整個[[匯出模組]]，這邊是只匯出檔案內的函數
```js
// 模組.js
exports = 函數名稱();
```
這樣匯入
```js
// app.js
const 模組 = require('./模組');
模組();
```

### middleware
[[Serving a Static File 回應有樣式的 HTML 檔案]]
### 建立 server
- 跟 node.js（ [[Server 建立（沒寫完）]]）比起來簡化很多
- 處理 [[HTTP request]]([[狀態碼]])
- [[Routing]]([[send 和 sendFile 回應(express)]])
```js
app.get('/', function (req, res) {	// 參數：網址，建立 server
	res.send('Hello World')			// 顯示文字
})
```
### 監聽
```js
app.listen(3000)					// 監聽 port
```

#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 