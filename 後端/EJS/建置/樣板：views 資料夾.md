### 樣板：views 資料夾
取代一般的 html 的 ejs 檔案必須都放在 `views` 資料夾下
```js
// index.ejs 一定要在 views 資料夾下才會運作，不然會出現 error
app.get("/", (req, res) => {
	res.render("index.ejs");			// 處理該 ejs 檔
})
```

## EJS 建置
>VS插件：[EJS Language support]

- npm: `npm install express nodemon ejs `
- Import: express, app, ejs
- middleware: [[Express 的 CSS 樣式環境建置 (Serving a Static File)]]
- [[樣板：views 資料夾]]
- [[生成樣板可用的變數：Routing for pattern]]
- port listening([[Express 建置]])