## findOneAndUpdate
>[[Update]] 會回傳整個列表，不會回傳更改過後的特定內容
```js
model.findOneAndUpdate(condition, update, options)
```
> [[Validators]] 預設不會重跑，options 可以加入 [[Update with Validators]] 來重跑
```js
Student.findOneAndUpdate(
	{ 要改的內容 },
	{ 更改後的內容 },
	{ new: true }		// find 有被更改的內容
).then((meg) => {
	console.log(meg)
})
```


## 使用 [[Instance Method]] 做出同樣效果
```js
// instance method
studentSchema.methods.addage = function() {
	this.age++;
}

Student.findOne({ name: 'Eric'})
	.then((data) => {
		data.addAge();
		console.log(data);
	}).catch(e => {
		console.log(e);
	})
```

#database #nosql #mongoose #mongodb #json #crud 