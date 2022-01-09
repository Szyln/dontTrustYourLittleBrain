# Passport.js
[npm](https://www.npmjs.com/package/passport)
[Passport Stretegies](https://www.passportjs.org/packages/)
Passport 提供 node 伺服器端使用各平台 OAuth 來登入
```
// passport 模組跟 + 使用的特定平台 stretegy
npm install passport passport-google-oauth20
```

# Google OAuth Passport 建置
## 安裝模組
```
npm install passport passport-google-oauth20
```
[passport-google-oauth20](https://www.passportjs.org/packages/passport-google-oauth20/)

```
專案/
|
|– routes/
|   |– auth-routes.js		# Authenticate Request
|– config/
|   |– passport.js			# Cofigure Strategy
|– views/
|   |– ejs 檔案
|– public/
|   |– css 檔案
|– .env
|– index.js
|– 
|– 
```
	
- [[Authenticate Requests]]
- [[Configure Strategy]]
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

#authentication #js #npm #nodeJs #module 