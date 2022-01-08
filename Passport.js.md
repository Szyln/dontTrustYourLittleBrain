# Passport.js
[npm](https://www.npmjs.com/package/passport)


Passport 提供 node 伺服器端使用各平台 OAuth 來登入
## Google 
```
npm install passport passport-google-oauth20
```
[passport-google-oauth20](https://www.passportjs.org/packages/passport-google-oauth20/)

### 新增資料夾 routes
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
#### middleware
```js
// 在 index.js 匯入
const authRoute = require('./routes/auth-route');

// middleware
// 檢查每次進來的 request 有沒有 /auth ，有的話就執行 authRoute
// authRoute 若被執行，就會辨識應該要回應 /login 還是 /google
app.use('/auth', authRoute);
```
>[[指定特定 Route 才能使用的 Middleware]]

### 新增 config 資料夾
```js
// passport.js
const passport = require('passport');
const GoogleStrategy = require('passport-google-oauth20');

passport.use(new GoogleStrategy({
		// 用 .env 存起來
    clientID: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
    callbackURL: "/auth/google/redirect"
  },
	() => {
		// passport callback
	}
 )
);
```
>[[dotenv（使用 env 變數）]]
#### .env 檔案
```
// string 不用加 '' or ""
GOOGLE_CLIENT_ID=從 google platform 取得的用戶端 ID
GOOGLE_CLIENT_SECRET=從 google platform 取得的用戶端密碼
```

### index.js
```js
// ./config/passport 貼過來用
// 不用 const 一個變數來存
require('./config/passport');
```
#authentication #js #npm #nodeJs #module 