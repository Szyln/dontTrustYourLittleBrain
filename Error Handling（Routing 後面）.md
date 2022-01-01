# Error Handling
[[Middleware 的位置]]

```js
app.use((err, req, res, next) => {
	console.log(err);
	res.status(500).send('有什麼東西出錯了，我們會儘快修復')
})
```