### save Jon to DB
```js
Jon.save()
	.then(() => {
		console.log('Jon has been saved into DB');
	})
	.catch(() => {
		console.log('error has happend.');
		console.log(e)
	});
```