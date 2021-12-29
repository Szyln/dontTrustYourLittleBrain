# API 提供更新資料的管道
>[[獲得請求後更新數據庫資料]]

一樣不用提供表單（[[EJS 提供用戶更新的資料的表單]]），也不用提供 edit 頁面（透過 HTTP Verb 即可）
```js
// 收到 put 更新後，更新數據庫
app.put('/students/:id', async (req, res) => {
	// 因為網頁上的 merit, other 沒有多包一層一個物件，需要先提出來
	let { id, name, age, merit, other } = req.body;
	try {
		res.send('感謝您，資料已更新');
		let data = await Student.findOneAndUpdate(
			{ id },
			{ id, name, age, scholarship:{ merit, other } },
			{
				new: true,
				runValidators: true,
			}
		);
		res.send('感謝您，資料已更新')
		
	} catch {
		res.status(404);
		res.send('更新失敗')
	}
})
```

>[[使用 Postman 發出表單請求]]，使用 PUT 請求即可

#api #js #restfulapi #api #crud #database #json 