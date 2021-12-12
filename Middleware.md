# Middleware(Mongoose)
[[Mongoose Method]]
- save 執行之前，

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