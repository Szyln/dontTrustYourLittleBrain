# Authenticate Requests
在 routes 資料夾內新增 auth-routes.js
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

// 匯出（給 index.js 用）
module.exports = Router; 
```
>[[Routing 中間使用 Middleware]]
>[[Configure Strategy]]
## middleware
- 請求包含 `/auth`？
	- 否：繼續執行 Life Cycle
	- 是：進到 `authRoute` 模組
		- 包含`/auth/login` ？
			- 是： render local login 頁面（login.ejs）
			- 否：包含`/auth/google` ？
				- 否：
				- 是：是否有設定 [[Configure Strategy]]？
					- 否：
					- 是：得到 ID 跟密碼與 Google 取得 scope 資料：導向 [[Web Application Client ID 設定#已授權的重新導向 URI]] ：[[Passport Verified Callback]]
```js
// 在 index.js 匯入
const authRoute = require('./routes/auth-route');

// middleware
// 檢查每次進來的 request 有沒有 /auth ，有的話就執行 authRoute
// authRoute 若被執行，就會辨識應該要回應 /login 還是 /google
app.use('/auth', authRoute);
```
>[[指定特定 Route 才能使用的 Middleware]]