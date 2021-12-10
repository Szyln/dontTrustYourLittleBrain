# Mongoose CRUD
[[Database 數據庫#C R U D]]
## Create: Define a Schema
如同 [[SQL create 製作表格]] create table 的動作，Mongoose 也會定義物件資料的類型
```js
// app.js
const studentSchema = new mongoose.Schema({
	name: string,
	age: Number,
	major: string,
	scholarship: {
		merit: Number,
		other: Number
	}
});
```
### create a model
model 就可以當成一個 [[MongoDB]] 的 collection 用了（[[MongoDB CRUD]]）
```js
// const 變數要大寫
// model 的 string 也要大寫、單數
const Student = mongoose.model('Student', studentSchema);
// mongoose 會自動把 model 轉成複數形式
```
> 因為 [[Mongoose 建置]]時已經指定 database 為 exampleDB 了，在操作指令時就不用寫 `db.` 了
> ```js
> db.collection.{ CRUD }		// 這是 [[MongoDB CRUD]] 寫法
> model.{ CRUD }				  // 這是 [[Mongoose]] 寫法
> ```
```

```
### create an object
```js
const Jon = new Studtent({
	name: 'John',
	age: 25,
	major: 'EE',
	scholarship: {
		merit: 2500,
		other: 1300
	}
})
```
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

### Insert
```js
Model.insertMany()
// 沒有 insertOne() ，因為直接用 save 就好
```
## Read
```js
Model.find()
```
### find
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
### update
[[MongoDB CRUD#Update]]
```js
model.update();
model.updateOne();
model.updateMany();
```
```js
// 直接設定更改前後的內容
Student.updateOne(
	{
		name: "Jon"
	},
	{
		name: "Sam"
	}
)
	.then((meg) => {
		console.log(meg);
	})
```
#database #nosql #json #npm #node