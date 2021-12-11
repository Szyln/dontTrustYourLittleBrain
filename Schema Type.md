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
- `Required`：必填，可以填入 array，寫入錯誤時的提示訊息
- `Default`：預設值

```js
// 另一種寫法
cost studentSchema = new mongoose.Schema({
	name: {
		type: String,
		required: [true, "You Forgot to enter the name."]
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
> 輸入的資料不完全符合 validators 的話，還是有機會送成功
> ```js
> const newStudent = new Student({
>     age: 18,
>     scholoarshipL { merit: "1500", other: "2000" }	// number 的類型欄位送出 string
> })
> ```
#json #dataType #nosql #mongoose 