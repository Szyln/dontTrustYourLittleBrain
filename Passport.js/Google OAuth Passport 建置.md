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
	
- [[Authenticate Requests]]：登出登入 routing、登入後流程設置
- [[Configure Strategy]](passport.js)
- [[建立 Google 的 OAuth 憑證]]
- [[Sessions in Passport]]


#passport #session #js #authentication #oauth