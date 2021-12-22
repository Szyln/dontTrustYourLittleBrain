### Request Handling(Express)
- 跟 node.js（ [[Server 建立]]）比起來簡化很多
- 處理 [[HTTP request]]([[狀態碼]])
- [[Routing]]([[send 和 sendFile 回應(express)]])
```js
app.get('/', function (req, res) {	// 參數：網址，建立 server
	res.send('Hello World')			// 顯示文字
})
```
#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server #routing 