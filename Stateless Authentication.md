# Stateless Authentication
>[[Stateful Authentication]]

客戶端成功登入後，server 會將客戶資料加密，回傳給客戶端（token），存在 [[Local Storage]]（客戶端不能更動）
之後客戶端傳送請求時，server 將 token 解密，確定這筆請求是不是有認證過

## 優點
- 不佔用伺服器資源：token 儲存在客戶端
- 後端無權限刪除資料：token 儲存在客戶端，後端無法修改
- 擴充容易：需要時從客戶端抓過來就好，不用準備儲存空間
- 簡易：他是一串字串，有利於傳輸
- 包含使用者資料：解密就好不用去數據庫花時間抓資料
- Digitally Signed：有數位簽證功能，安全性
- 支援多種程式語言
## 缺點
- 後端不能修改內容


#session #authentication #oauth 