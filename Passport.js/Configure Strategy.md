# Configure Strategy
存取
- 客戶端 ID 
- 客戶端密碼

得到客戶端 ID 跟密碼與 Google 取得資料後，導向 [[Configure Strategy]] 設定的 callbackURL

> - callbackURL 需要在	Google Cloud Platform 設定：[[Web Application Client ID 設定]]
> - 導過去之後的行為：[[Passport Verified Callback]]


# passport.js
新增 config 資料夾，新增 passport.js 檔案 

```js
// config/passport.js
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
>- callbackURL 需要設定：
>	 [[建立 Google 的 OAuth 憑證]]：[[Web Application Client ID 設定]]

## 匯出 index.js
>[[匯出模組]]
```js
// ./config/passport 貼過來用
// 不用 const 一個變數來存
require('./config/passport');
```

