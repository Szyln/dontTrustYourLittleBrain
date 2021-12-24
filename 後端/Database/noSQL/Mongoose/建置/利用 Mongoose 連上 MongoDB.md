# 利用 Mongoose 連上 MongoDB
```js
// connect to mongoDB
// 要設定連接成功或失敗的效果
// 連到一個 database（exampleDB 為例，可自訂）
mongoose.connect('mongodb://localhost:27017/exampleDB', {
	useNewUrlParser: true,
	useUnifiedTopology: true,
})

	.then(() => {
		console.log('Connected to MongoDB.');
	})

	.catch((err) => {
		console.log('Failed.');
		console.log(err);
	})
```

>`mongoose.connect()`連結到名為 `exampleDB` 的 database

#database #json #nosql #node #mongoose