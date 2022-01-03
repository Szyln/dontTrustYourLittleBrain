# Cookie
- 也是一個儲存資料的地方（類似[[Storage]]）
- 但跟 [[Storage]] 不同的是，他是為了讓伺服器端讀取的，前者反之
- 客戶端發送請求 [[HTTP request]] 時候，[[Cookie]] 就會跟著發出去，[[Storage]] 不會
- [[Key-Value Pair]]

---

# res.cookie
傳送 cookie 給瀏覽器端
```js
app.get('/', (req, res) => {
	res.cookie('name', 'Wilson');
})
```
也可在 [[Postman]] 看到這些資料
# req.cookie
使用 cookie，需要安裝 middlewarea 模組[[cookie-parser]]
```js
app.get('/', (req, res) => {
	console.log(req.cookies);
})
```