# Configure Strategy
存取
- 客戶端 ID 
- 客戶端密碼

- 如果客戶端輸入 google 的帳密正確後，導向 [[Web Application Client ID 設定#已授權的重新導向 URI]] ：[[Passport Verified Callback]]


# passport.js
新增 cofig 資料夾，新增 passport.js 檔案 

```js
// cofig/passport.js
const passport = require('passport');
const GoogleStrategy = require('passport-google-oauth20');
const User = require('../models/user-model');

passport.use(new GoogleStrategy({
		// 用 .env 存起來
    clientID: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
		// 
    callbackURL: "/auth/google/redirect"
  },
	// done 是一個 callback function
	// passport verified callback
	(accessToken, refreshToken, profile, done) => {
		console.log(profile);
		User.findOne({googleID: profile.id})
			.then((foundUser) => {
				if(foundUser) {
					console.log('User already exist');
					done(null, foundUser);
				} else {
					new User({
						name: profile.displayName,
						googeID: profile.id,
						thumbnail: profile.photos[0].value,
					}).save().then((newUser) => {
						console.log('成功透過 google 新增帳戶');
						done(null, newUser);
					})
				}
			})
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

