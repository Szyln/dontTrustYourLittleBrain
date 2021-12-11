# Mongoose Find(Read)
```js
Model.find()
```
```js
Student.find({}).then(data => {
	console.log(data);
})
// 執行後會在終端看到搜尋結果
// 不論幾個 object 符合條件，都會包在 array 裡面
```
```js
Student.findOne({ name: 'John' })
	.then(data => {
		console.log(data);
})
// 執行後會在終端看到搜尋結果
// 回傳一個 object
```
> `find` 還有很多[連合技](https://mongoosejs.com/docs/api/model.html)


> 也可以配合 [[MongoDB CRUD#比較 comparison operator]] 來做更複雜的篩選
> ```js
> Student.find({ "scholarship.merit" : {$gte: 1500} }).then((data) => {
> 	console.log(data);
> })
> ```
## Find and Update
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

#database #nosql #mongoose #mongodb #json #crud 