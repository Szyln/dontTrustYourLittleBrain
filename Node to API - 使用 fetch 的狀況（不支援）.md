# Node to API - 使用 fetch 的狀況（不支援）
[[Node to API#Routing]]
Node 不支援 [[Fetch]] 功能，在 node 裡想要串 API 要注意不要這樣寫
```
UnhandledPromiseRejectionWarning: ReferenceError: fetch is not defined
```

```js
app.get('/:city', async (req, res) => {
	let { city } = req.params;
	let url =`API 給的 endpoint`;
	let data = await fetch(url);
	let dataJson = await data.json();
	console.log(dataJson);
	res.render('weather.ejs');
});
```
## 方法
有兩種
- https.get()
- 

#js #node #api #promise #expressJs #ejs 