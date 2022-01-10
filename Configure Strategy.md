# Configure Strategy
新增 cofig 資料夾，新增 passport.js 檔案 
```js
// cofig/passport.js
const passport = require('passport');
const GoogleStrategy = require('passport-google-oauth20');

passport.use(new GoogleStrategy({
		// 用 .env 存起來
    clientID: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
		// 
    callbackURL: "/auth/google/redirect"
  },
	() => {
		// passport callback
	}
 )
);
```
> - [[dotenv（使用 env 變數）]]
>	 - [[passport-google-oauth20 的 .env 變數]]
>	callbackURL：[[建立 Google 的 OAuth 憑證]]：[[Web Application Client ID 設定]]

## 匯出 index.js
>[[匯出模組]]
```js
// ./config/passport 貼過來用
// 不用 const 一個變數來存
require('./config/passport');
```

