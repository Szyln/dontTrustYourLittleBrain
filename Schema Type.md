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
		required: [true, "This is Required"]
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
> // 可以成功
> ```

> 如果送出不存在的 Schema ，不會產生 error ，但也不會存進 DB 裡面

### 更詳細的 Validators(Built-in Validators)
#### required
值可以是：
- boolean
- array: `[true, "沒有填的時候跳出的錯誤提示"]`
- function: `function() { return this.其他欄位 > 3; }`
```js
cost studentSchema = new mongoose.Schema({
	name: { 
		type: String,
		required: [true, "This is Required"]
	},
})
```

```js
cost breakfastSchema = new mongoose.Schema({
	bacon: {
		type: Number,
		required: true
	},
	drink: {
		type: String,
		required: function() {
			return this.bancon > 3;		// 如果 bacon 點了三片以上就必須點飲料
		}
	},
})
```


#json #dataType #nosql #mongoose 