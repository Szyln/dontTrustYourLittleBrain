# Error Handling
[[Middleware 的位置]]
Error Handling 會放在 Routing 後面，可以對應程式出錯時，使用者會看到什麼畫面，而不是看到一堆用戶看不懂的內容

- [[Error Handling（Routing 後面）#同步的寫法]]
- [[Error Handling（Routing 後面）#非同步的寫法]]


> 如果是網址的亂打會用：[[Routing for all 回應亂打的網址]]，放在 Routing 的最後一個

---

## 同步的寫法
```js
// routing 沒有使用 promise 的話
// error handler
app.use((err, req, res, next) => {
	console.log(err);
	res.status(500).send('有什麼東西出錯了，我們會儘快修復');
	// 可以在這邊提供一個表單問遇到什麼問題
})

// port listen
```

## 非同步的寫法
>- [[Mongoose]]：[[Find(Read)]]
>- [[Async（目錄）]]
```js
// routing 有用到 promise 的話：
app.get('/', async(req, res, next) => {
	try {
		let foundData = await Monkey.findOne({ name: 'Ban'});
		res.send(foundData);
	} catch(e) {
		next(e);			// 這個 error 就會傳到下一個 middleware(error handler)
	}
})

// error handler
app.use((err, req, res, next) => {
	console.log(err);
	res.status(500).send('有什麼東西出錯了，我們會儘快修復');
	// 可以在這邊提供一個表單問遇到什麼問題
})

```

## 處理 [[Validators]] 錯誤的寫法

#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 