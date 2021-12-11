# Validators
[[SQL create 製作表格]] 中有提到 [[Constraints]] 可以將資料內容做規範

其中所有 [[Schema Type]] 都可以用的是：
- [[required]]：必填
- Default：預設值

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

## 特性
輸入的資料不完全符合 validators 的話，還是有機會送成功
```js
const newStudent = new Student({
	age: 18,
	scholoarshipL { merit: "1500", other: "2000" }	
	// 在 number 的類型欄位送出 string
})
// 可以成功
```

> 如果送出不存在的 Schema ，不會產生 error ，但也不會存進 DB 裡面
