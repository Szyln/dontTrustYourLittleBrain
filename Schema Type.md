# Schema Type(Mongoose)
[[Mongoose CRUD#Create Define a Schema]] 的時候，需要定義資料類型
```js
// 另一種寫法
cost studentSchema = new mongoose.Schema({
	name: {
		type: String
	},
	age: {
		type: Number
	}
	scholarship {
		merit: {
			type: Number
		}
		other: {
			type: Number
		}
	}
})
```
## Validators
[[SQL create 製作表格]] 中有提到 [[Constraints]] 可以將資料內容做規範

其中所有 [[Schema Type]] 都可以用的是：
- `Required`：必填
- `Default`：預設值

```js
// 另一種寫法
cost studentSchema = new mongoose.Schema({
	name: {
		type: String,
		required: true
	},
	age: {
		type: Number,
		required: true,
		default: 18,
	}
	scholarship {
		merit: {
			type: Number
		}
		other: {
			type: Number
		}
	}
})
```
#json #dataType #nosql #mongoose 