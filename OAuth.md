# OAuth(Open Authentication)
- 使用其他平台（Google, Facebook......）來登入
- 需要使用 JS 的 Library： [[Passport.js]] 來與該平台溝通

> [[Library 跟 Framework 的差別]]


## 建立 Google 的 OAuth 憑證
[Google Cloud Platform](https://console.cloud.google.com/)
- 建立專案 -> 結束後到「憑證」的頁面
- 憑證 -> 建立憑證 -> OAuth 用戶端 ID -> 設定同意畫面 -> 外部
	- 應用程式名稱：隨意
	- 使用者支援電子郵件：自己的 email
	- 應用程式首頁：`http://localhost:8080`
	- 開發者聯絡資訊：自己的 email

- 再回到「憑證」頁面 -> 建立憑證 -> OAuth 用戶端 ID
	- 應用程式種類：網路應用程式
	- 名稱：任意
- 「OAuth 用戶端已建立」：得到用戶端 ID 跟密碼

## 使用 [[Passport.js]]
