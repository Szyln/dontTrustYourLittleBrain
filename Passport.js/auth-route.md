# auth-route
>[[Authenticate Requests]]

在 routes 資料夾內新增 auth-routes.js



---
## 匯入(auth-route)
```js
// local login, oauth
const router = require('express').Router();
const passport = require('passport');
// 註冊加密用： bcrypt
const bcrypt = require('bcrypt');
// 
const session = require('express-session');
const flash = require('connect-flash');
```
>[[bcrypt]]
>[[express-session]]
>[[connect-flash]]

## 看客戶端要用 google 還是本地登入
- 請求包含`/auth/login` ？
	- 是： render local login 頁面（login.ejs）
	- 否：包含`/auth/google` ？
		- 否：
		- 是：檢查是否有設定 [[Configure Strategy]]
			- 否：
			- 是：得到客戶端 ID 跟密碼與 Google 取得資料後，導向 [[Configure Strategy]] 設定的 callbackURL


> - callbackURL 需要在	Google Cloud Platform 設定：[[Web Application Client ID 設定]]
> - 導過去之後的行為：[[Passport Verified Callback]]
```js

router.get('/login', (req, res) => {
	res.render('login', { user: req.user });
});

router.get('/google',
	// 這是一個 middleware
	// 透過 passport 與取得 google 驗證
	// 對應 config/passport.js 的設定
	passport.authenticate('google', {
		// 取得 google 的 profile 資料
		scope: ['profile'],
	});
);
```
>[[req.user]]

### （選用）google 登入可選擇登入帳號
```js
router.get('/google',
	passport.authenticate("google", {
		scope: ["profile", "email"],
		prompt: "select_account",
	})
);
```
## 用戶登入後
```js
// 取得 configure strategy 的資料後
router.get('/google/redirect', 
	// middleware
	// 到 config passport verified callback
	passport.authenticate('google'),
	(req, res) => {
		res.redirect('profile');
	}
)
```
>- [[Routing 執行時的 Middleware（Route 中間）]]
>- [[Configure Strategy]]
>- [[profile-route]]

## Local Signup
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
## 用戶登出
[[req.logout()]]
```js
// login route 後面
router.get('/logout', (req, res) => {
	req.logout();
	res.redirect('/');
})
```

## 匯出
```js
// 匯出（給 index.js 用）
module.exports = Router; 
```