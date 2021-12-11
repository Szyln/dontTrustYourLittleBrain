# Instance Method
- Instance Method
- Stactic method

[[Create#Define a Schema]] 之後，可以設定 [[Instance Method]] 供
```js
// create an instance method
student.Schema.methods.totalScholarship = function() {
	return this.scholarship.merit + this.scholarship.other;
}

// create a model
const Student = mongoose.model('Student', studentSchema);

Student.find({ name: 'Eric' })
	.then(data => {
		data.totalScholarship();
		console.log(result)
	}).catch(e => {
		console.log('error');
		console.log(e);
	})
```

#database #mongoose