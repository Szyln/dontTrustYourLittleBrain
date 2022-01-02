# 處理 [[Validators]] 錯誤的寫法
```js
// define a Schema
const monkeySchema = new mongoose.Schema({
	name: {
		type: String,
		minlength: 3,
	}
})
// create a model
const Monkey = mongoose.model('Monkey', monkeySchema);

// routing
app.get('/', async(req, res, next) => {
	try {
		// create an object：這邊假設一個不符合 validators 的物件
		let newMonkey = new Monkey({ name: 'S' });
		// save to database
		newMonkey.save()
			.then(() => {
				res.send('成功儲存資料');
			}).catch((errMessage) => {
				// 網頁會顯示一個 error 物件，不會跳到 middleware
				res.send(errMessage);
			});
	} catch(e) {
		next(e);
	}
})
```
>- [[Validators]]
>- [[透過 Mongoose 存入 MongoDB(Save)]]

#mongoose #json #js #database #validators #crud #node #expressJs 