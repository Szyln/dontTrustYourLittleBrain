# writeFile
```js
// 定義在 'save' 之前要做什麼事
// writeFile: 建立一個檔案，指定寫入什麼內容
studentSchema.pre('save', async function(){
	fs.writeFile('history.txt', "One data is trying to be saved.", (e) => {
		if (e) throw e;
	})
})
```

預設是可以在該檔案寫內容，每次使用這個功能，都會覆寫掉原本的內容

