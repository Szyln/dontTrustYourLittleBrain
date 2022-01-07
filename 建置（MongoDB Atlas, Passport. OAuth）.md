# 建置（MongoDB Atlas, Passport. OAuth）
>- [ ] 為什麼是叫 index.js 而不是 app.js？
>- [ ] `app.use(express.json());` 是做什麼的？


>- [[匯入模組]]
>- [[dotenv]]
```js
// index.js
// import express, app, mongoose, dotenv
// dotenv.config();
```

>- [[利用 Mongoose 連上 MongoDB]]
>	- [[MongoDB Atlas]] 
```js
mongoose.connect('mongodb+srv://sz:<這裡要置換成密碼>@cluster0.hk85a.mongodb.net/<這裡要置換成想要命名的數據庫名稱>?retryWrites=true&w=majority').then(() => {
		console.log('成功連上 mongodb atlas');
	}).catch((err) => {
		console.log(err);
})
```

## [[Middleware(express)]]
>- [[EJS with Express 的基本設定]]
>[[body-parser]]
```js
app.set('view engine, 'ejs);
app.use(express.json());
app.use(express.urlencoded({extend: true}))
```