## 本地註冊
這個註冊完，存到數據庫後不會有 googleID
```js
// 匯入 bcrypt 做註冊密碼加密
// 匯入 User model
router.get('/signup', (req, res) => {
	res.render('signup', { user: req.user });
})

router.post('/signup', async (req, res) => {
	console.log(req.body);
	let { name, email, password } = req.body;
	// 檢查 email 是否已註冊
	const emailExist = await User.findOne({ email });
	if (emailExist) return res.status(400).send('此 email 已註冊');
	// 加密
	const hash = await bcrypt.hash(password, 10);
	let newUser = new User({ name, email, password: hash});
	try {
		const savedUser = await newUser.save();
			// 通常不會顯示給用戶看這個，可以 flash（下一段）
			res.status(200).send({
				msg: '用戶已儲存',
				savedObj: savedUser,
			});
	} catch {
		res.status(400).send(err);
	}
	res.send('感謝您的註冊');
})
```
>[[Hash Function]]：[[bcrypt]]


### 註冊成功
>[[Flash]]
```js
// 需要會匯入 express-session, connect-flash

```