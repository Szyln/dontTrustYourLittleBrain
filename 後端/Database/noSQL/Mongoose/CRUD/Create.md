# Create(Mongoose)
## 建立架構
### Define a Schema
如同 [[SQL create 製作表格]] create table 的動作，Mongoose 也會定義物件的 [[Schema Type]]
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
> 如果要更複雜的定義 [[Validators]]
> 想要做些功能 [[Instance Method]]
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

## 建立細項（可以使用 CRUD）
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

## Insert
```js
Model.insertMany()
// 沒有 insertOne() ，因為直接用 save 就好
```

#mongoose #mogodb #database #crud #nosql #json