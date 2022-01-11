# Stateless Authentication
>[[Stateful Authentication]]

客戶端成功登入後，server 會將客戶資料加密，回傳給客戶端（token），存在 [[Local Storage]]（客戶端不能更動）
之後客戶端傳送請求時，server

## 優點
- 後端無權限刪除資料：token 儲存在客戶端，後端無法修改
- 
## 缺點
- 後端有權限刪除資料：如果在後端刪掉了這個對應的 ID，客戶端持有的資料就會失效
- 佔據伺服器資源：因為資料都存在 server，隨著登錄的用戶增加，server 的資源也會被佔用
- 很難擴充：如果伺服器佔滿了，要擴充新的伺服器，要為了新的伺服器寫不同的規則
- 安全性：cookies 可以透過客戶端修改，可能真的試出別人的資料
