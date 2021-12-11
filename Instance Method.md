# Instance Method
- Instance Method
- Stactic method

[[Create#Define a Schema]] 之後，可以設定 [[Instance Method]] 供 model 使用
[[Find(Read)]]
```js
// create an instance method
studentSchema.methods.totalScholarship = function() {
	return this.scholarship.merit + this.scholarship.other;
}

// create a model
const Student = mongoose.model('Student', studentSchema);


// find 會回傳 array，要用 findOne (回傳object)
Student.findOne({ name: 'Eric' })	
	.then(data => {
		let result = data.totalScholarship();
		console.log(result)
	}).catch(e => {
		console.log('error!');
		console.log(e);
	})
```
> 第一段要注意，有用 [[this]]，不可以隨意改成[[JavaScript/資料類型/Function/4.箭頭函式 arrow function]]
#database #mongoose #crud 