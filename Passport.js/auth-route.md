# auth-route
>[[Authenticate Requests]]

在 routes 資料夾內新增 auth-routes.js

- 請求包含`/auth/login` ？
	- 是： render local login 頁面（login.ejs）
	- 否：包含`/auth/google` ？
		- 否：
		- 是：檢查是否有設定 [[Configure Strategy]]
			- 否：
			- 是：得到客戶端 ID 跟密碼與 Google 取得資料後，導向 [[Configure Strategy]] 設定的 callbackURL


> - callbackURL 需要在	Google Cloud Platform 設定：[[Web Application Client ID 設定]]
> - 導過去之後的行為：[[Passport Verified Callback]]

---

```js
const router = require('express').Router();
const passport = require('passport');

router.get('/login', (req, res) => {
	res.render('login');
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
>- [[Routing 中間使用 Middleware]]
>- [[Configure Strategy]]
>- [[profile-route]]

## 匯出
```js
// 匯出（給 index.js 用）
module.exports = Router; 
```