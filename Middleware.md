# Middleware(Mongoose)
[[Mongoose Method]]
[[Mongoose 建置]]
- 可以定義哪些動作之前（pre）

```js
const fs = require('fs') 	// file system

// 定義在 'save' 之前要做什麼事
studentSchema.pre('save', async function(){
	fs.writeFile('presave.txt', "One data is trying to be saved.", (e) => {
		if (e) throw e;
	})
})
```

#database #nosql #json #mongoose 