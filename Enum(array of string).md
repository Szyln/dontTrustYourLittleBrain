# Enum(array of string)
> enumerate: 枚舉


```js
const studentSchema = new mongoose.Schema({
	major: {
		type: string,
		enum: ["Chem", ],
		default: "尚未選擇"
	} 
})
```
> 忘記過程可以看詳細：[[Create]], [[Schema Type]]
> 
#database #nosql #mongoose #mongodb #validators