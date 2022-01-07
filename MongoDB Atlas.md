# MongoDB Atlas
雲端版本的 [[MongoDB]]

## Network Access
Current 跟 Anywhere IP 都新增

## Database Access
新增 User

## Database(Cluster)
按 Connect -> Connect your application

### Add your connection string into your application code
這段的 URI 把他貼到 mongoose.connect 裡面
>[[利用 Mongoose 連上 MongoDB]]
```js
mongoose.connect('貼到這，<password> 要記得改成 User 的密碼')

	.then(() => {
		console.log('Connected to MongoDB Atlas.');
	})

	.catch((err) => {
		console.log('Failed.');
		console.log(err);
	})
```

#js #json #expressJs #mongoose #mogodb 