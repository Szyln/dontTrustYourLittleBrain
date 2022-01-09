# Authenticate Requests
在 routes 資料夾內新增 auth-routes.js
```js
const router = require('express').Router();
const passport = require('passprort');

router.get('/login', (req, res) => {
	res.render('login');
});

router.get('/google',
	// 這是一個 middleware
	// 透過 passport 與取得 google 驗證
	passport.authenticate('google', {
		// 取得 google 的 profile 資料
		scope: ['profile'],
	});
);

// 匯出（給 index.js 用）
module.exports = Router; 
```
>[[Routing 中間使用 Middleware]]
## middleware
```js
// 在 index.js 匯入
const authRoute = require('./routes/auth-route');

// middleware
// 檢查每次進來的 request 有沒有 /auth ，有的話就執行 authRoute
// authRoute 若被執行，就會辨識應該要回應 /login 還是 /google
app.use('/auth', authRoute);
```
>[[指定特定 Route 才能使用的 Middleware]]