# 使用 Routing for pattern 顯示特定數據庫物件
>[[Routing for pattern 回應有規律的網址]]
>[[Find(Read)]]
```js
app.get('student/:id', async (req, res) => {
	let { id } = req.params;
	try {
		let data = await Student.findOne({ id });
		res.render('studentPage.ejs', { data })
	} catch(e) {
		res.send('該 ID 尚未被登錄');
		console.log(e);
	}
})
```

#js #npm #node #expressJs #mongoose #database #form #ejs #backEnd #routing 