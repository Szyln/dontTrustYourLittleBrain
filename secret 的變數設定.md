# secret 的變數設定
- 為了加密內容，不應該直接在 app.js 內輸入 SE
- 透過 [[Node.js]] 的內建全域物件： [[process(node)]] 達成
- 需要使用 [[dotenv]] npm 模組，設定變數


## 在 .env 設定 secret 
```
// .env 裡面
SECRET=THISISMYTOPSECRET
```
可以在 [[express-session]] 中使用

## 使用 env 的變數
```js
app.use(session({
	// 透過 dotenv 模組存入一個 env 變數做使用
	secret: process.env.SECRET,
	resave: false,
	saveUninitialized: false
}))
```


#js #node #expressJs #session #npm #module 