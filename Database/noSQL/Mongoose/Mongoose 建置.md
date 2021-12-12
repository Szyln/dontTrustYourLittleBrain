# [[Mongoose]] 建置
```
npm install mongoose
```
寫在 middleware 前
```js
const express = require('express');
const app = express();
const ejs = require('ejs');
const mongoose = require('mongoose');
  
// connet to mongoDB
// 要設定連接成功或失敗的效果
// 連到一個 database
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
mongoose 的內容寫在中間這裡
```js
// define a schema
// create an instance method
// create an static method
// define middleware(mongoose)
// create a model
// create an object
// save
```

```js
// middleware
app.use(express.static('public'));
  
app.get('/', (req, res) => {
	res.render('index.ejs');
})

app.listen(3000, () => {
	console.log("running on port 3000");
})
```
>`mongoose.connect()`連結到名為 `exampleDB` 的 database


#database #json #nosql #node #mongoose