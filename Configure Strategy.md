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
    callbackURL: "/auth/google/redirect"
  },
	() => {
		// passport callback
	}
 )
);
```
>[[dotenv（使用 env 變數）]]
> [[passport-google-oauth20 的 .env 變數]]
