# Middleware
- save 執行之前，

```js
const fs = require('fs') 	// file system

studentSchema.pre('save', async function(){
	fs.watchFile('presave.txt', "One data is trying to be saved.", (e) => {
		if (e) throw e;
	})
})
```