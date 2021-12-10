# 302 Found
指原本存在，但目前已經移除
```js
app.get("/舊網頁", (req, res) => {
	res.status(302);
	res.sendFile(path.join(__dirname, "moved.html"));
})
```

#js #expressJs #node #backEnd #npm
