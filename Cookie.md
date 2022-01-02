# Cookie
- 也是一個儲存資料的地方（類似[[Storage]]）
- 但跟 [[Storage]] 不同的是，他只能被伺服器端讀取，前者反之
- 客戶端發送請求 [[HTTP request]] 時候，[[Cookie]] 就會跟著發出去，[[Storage]] 不會
- [[Key-Value Pair]]

---

# res.cookie
```js
app.get('/', (req, res) => {
	res.cookie('name', 'Wilson');
})
```

# req.cookie