# 建置生命週期（MongoDB Atlas, Passport. OAuth）
>- [ ] 為什麼是叫 index.js 而不是 app.js？
>- [ ] `app.use(express.json());` 是做什麼的？


>- [[匯入模組]]
>- [[dotenv（使用 env 變數）]]
```js
// index.js
// import express, app, mongoose, dotenv
// dotenv.config();
```

>- [[利用 Mongoose 連上 MongoDB]]
>	- [[MongoDB Atlas]]
```js
// 連結的 URI 要存到 env 
mongoose.connect(process.env.DB_CONNECT).then(() => {
		console.log('成功連上 mongodb atlas');
	}).catch((err) => {
		console.log(err);
})
```

## [[Middleware(express)]]
>- [[EJS with Express 的基本設定]]
>- [[body-parser]]
```js
app.set('view engine, 'ejs);
app.use(express.json());
app.use(express.urlencoded({extend: true}))
```