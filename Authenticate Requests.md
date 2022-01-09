## Authenticate Requests
在 routes 資料夾內新增 auth-routes.js
```js
const router = require('express').Router();
const passport = require('passprort');

router.get('/login', (req, res) => {
	res.render('login');
});

router.get('/google', (res, req) => {
	// 透過 passport 與取得 google 驗證
	passport.authenticate('google', {
		// 取得 google 的 profile 資料
		scope: ['profile'],
	});
});

// 匯出（給 index.js 用）
module.exports = Router; 
```