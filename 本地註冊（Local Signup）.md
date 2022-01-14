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
>[[Sessions in Passport]]
>[[Flash]]/Users/sz/不同步資料/前端學習/wilson/project 5/config/passport.js
>- [[express-session]]
>- [[connect-flash]]
>- [[cookie-session]]
```js
// index.js(why
// 為什麼這段又把 cookie-session 刪掉了
// 突然又不用 cookie-session 的 middleware 了
// ?????
// 需要會匯入 express-session, connect-flash

app.use(session({
	secret: process.env.SECRET,
	resave: false,
	saveUninitialized: false
	
}))
// session in passport
app.use(passport.initialize());
app.use(passport.session());
// flash
app.use(flash());
app.use((req, res, next) => {
	res.locals.sucess_msg = req.flash('sucess_msg');
	res.locals.error_msg = req.flash('error_msg');
	next();
}) 
```

#### message.ejs (partials)
```html
<% if (error_msg != '') { %>
	<div class="alert alert-warning alert-dismissible fade show" role="alert">
		<strong><%= error_msg %> </strong>
	</div>
<% } %>	
<!-- break -->
<% if (sucess_msg != '') { %>
	<div class="alert alert-warning alert-dismissible fade show" role="alert">
		<strong><%= sucess_msg %> </strong>
	</div>
<% } %>	
```