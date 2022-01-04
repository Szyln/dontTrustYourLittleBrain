# Session
- [[Cookies and Sessions 的差別]]在 [[Cookie]] 無法加密且容量較小
- 需使用 [[express-session]] 模組

## req.session
```js
app.get('/', (req, res) => {
	console.log(req.session);			// 目前只有存在伺服器記憶體，伺服器關掉就會清空
})
```



#js #backEnd #server #storage #expressJs