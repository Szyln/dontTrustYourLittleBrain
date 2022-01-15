# Configure Strategy
存取
- 客戶端 ID 
- 客戶端密碼

得到客戶端 ID 跟密碼與 Google 取得資料後，導向 [[Configure Strategy]] 設定的 callbackURL

> - callbackURL 需要在	Google Cloud Platform 設定：[[Web Application Client ID 設定]]
> - 導過去之後的行為：[[Passport Verified Callback]]


## passport.js
新增 config 資料夾，新增 passport.js 檔案 


## 模組設定
>- [[Google OAuth Passport 建置]]
>- [[passport-local]]
>- [[bcrypt#檢查密碼]]：登入時加密
```js
// config/passport.js
const passport = require('passport');
const GoogleStrategy = require('passport-google-oauth20');
const User = require('../models/user-model');
const LocalStrategy = require('passport-local');
const bcrypt = require('bcrypt');
```

### 在 index.js 匯入
```js
// index.js
// 不用 const 一個變數來存
require('./config/passport');
```
>[[建置生命週期（MongoDB Atlas, Passport. OAuth）]]

## Stretegy
- [[Configure Strategy(passport-google)]]
- [[Configure Strategy(passport-local)]]