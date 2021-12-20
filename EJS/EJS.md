# EJS(Embedded JavaScript)
- 一種[[樣板語言]](template language)，可以做樣板管理
- 中文：嵌入式 JS
- 一種[[樣板語言]]，在 JS 的環境下寫 HTML
- [[8.layout]]

## 環境建置
>VS插件：[EJS Language support]

- npm: `npm install express nodemon ejs `
- Import: express, app, ejs
- middleware: [[Express 的 CSS 樣式環境建置 (Serving a Static File)]]
- [[樣板：views 資料夾]]
- [[生成樣板可用的變數：Routing for pattern]]

## 撰寫
- [[EJS 撰寫規則]]
- [[EJS 回應表單]]


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