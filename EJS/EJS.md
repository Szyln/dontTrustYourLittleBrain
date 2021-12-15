# EJS(Embedded JavaScript)
一種[[樣板語言]](template language)，可以做樣板管理
跟目前學的語言類似ㄠ

- 中文：嵌入式 JS
- 一種[[樣板語言]]用 JS 生成 HTML 
- [[8.layout]]

## 環境建置
>VS插件：[EJS Language support]
### 安裝
```
npm install express nodemon ejs 
```
### 樣式：middleware
依循[[Middleware：Serving a Static File 回應有樣式的 HTML 檔案]]建立 `middleware`，樣式檔案要放在 `public` 資料夾內
```js
// 匯入三個模組： express, app, ejs

// middleware
app.use(express.static("public"));

app.get("/", (req, res) => {
	res.send("HomePage");
})

app.listen(300, () => {
	console.log("Server is running on port 3000")
})
```
### 樣板：views 資料夾
取代一般的 html 的 ejs 檔案必須都放在 `views` 資料夾下
```js
// index.ejs 一定要在 views 資料夾下才會運作，不然會出現 error
app.get("/", (req, res) => {
	res.render("index.ejs");			// 處理該 ejs 檔
})
```
### 在 HTML 內使用變數：Routing for pattern
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
> L51：[[從物件中提取屬性到變數中 Destructing an object]]
> L53：`{ name }` 為 `{ name: name }` 的語法糖

## 在 EJS 檔案內撰寫 HTML 
EJS 可以當成就是在 JS 環境寫 HTML，所以也可以在裡面寫 JS
### 文法
```ejs
<標籤><%= 要取得這個值到 HTML 的話 %></標籤>
<% 撰寫純 JS code 的話 %>

```
### 範例
#### 單純用變數
```ejs
// person.ejs
// 網址打什麼都會顯示在 name 變數裡面
<h1><%= name %></h1>
```
#### for 迴圈
```ejs
<body>
	<%for (let = 0; i < 10; i++) {%>
		<p><%= i %><p>
	<% } %>
</body>
```

## [[EJS 回應表單]]
## 搭配[[Database 數據庫]]

```js
app.get("/", (req, res) => {
	// 有個 array ，通常數據庫都會給這樣格式的資料
	const languages = [
		{ name: "python", rating: 9.5 popularity: 9.7}, 
		{ name: "java" ......}
]

	
	res.render("index.ejs", { languages });
});
```

```ejs
<% languges.forEach(lang => { %>
<tr>
	<td><%= lang.name %></td>
	<td><%= lang.popularity %></td>
</tr>
<% }) %>
```
#npm #gulp #html #js #ejs