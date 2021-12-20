### 生成樣板可用的變數：Routing for pattern
[[Routing#Routing for pattern 回應有規律的網址]]
可以將輸入的網址部分設定為變數
```js
// 匯入三個模組： express, app, ejs

// middleware
app.use(express.static("public"));

// index.ejs 一定要在 views 資料夾下才會運作
app.get("/:name", (req, res) => {
	let { name } = req.params
	// ejs 檔案後的物件，可以供 ejs 檔案當變數使用
	res.render("person.ejs", { name });
})
```
> [[從物件中提取屬性到變數中 Destructing an object]]
> `{ name }` 為 `{ name: name }` 的語法糖