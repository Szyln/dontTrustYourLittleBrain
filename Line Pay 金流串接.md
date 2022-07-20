---
title: "Line Pay 金流串接"
tag: 
- 
---

##  Line Pay 金流串接
### 步驟
1. 註冊
2. 金鑰


## [npm](npm.md)
- [axios](axios.md)
- [dotenv（使用 env 變數）](dotenv（使用%20env%20變數）.md)
- crypto-js：加密用

## 專案
### 瀏覽器
- 登入後 post 付款
### 手機
用戶掃 QRcode 付款
### server
- 處理 post 
- 傳給 line server
- ㄑ

### db

兩筆訂單
資料有
- 品項
- 單價

### line pay 伺服器
處理完後要 redirect

## 用戶使用步驟
- 按訂單
- 進到 line pay
- 付款
- 付款完成

Casper

20220720

-   直播連結：[](https://youtu.be/nEjVIeDE-Ro)[https://youtu.be/nEjVIeDE-Ro](https://youtu.be/nEjVIeDE-Ro)
    
    > 麻煩按讚、訂閱、開啟小鈴鐺
    
-   文件連結：[](https://hex.school/2W3yi)[https://hex.school/2W3yi](https://hex.school/2W3yi)
    

講師：卡斯伯

-   卡斯伯的 Blog：[](https://www.casper.tw/)[https://www.casper.tw/](https://www.casper.tw/)
-   卡斯伯的粉絲頁：[](https://www.facebook.com/WccCasper/)[https://www.facebook.com/WccCasper/](https://www.facebook.com/WccCasper/)
-   活動行事曆：[](https://www.hexschool.com/calendar/)[https://www.hexschool.com/calendar/](https://www.hexschool.com/calendar/)

> 近期活動

[React 新手讀書會 | 六角學院](https://www.hexschool.com/2022/06/27/2022-06-27-react-study-circle/)

## 活動課綱

### 註冊 LINE Pay

-   LINE Pay 文件

[](https://pay.line.me/tw/developers/techsupport/sandbox/testflow?locale=zh_TW)[https://pay.line.me/tw/developers/techsupport/sandbox/testflow?locale=zh_TW](https://pay.line.me/tw/developers/techsupport/sandbox/testflow?locale=zh_TW)

1.  註冊測試環境
2.  使用測試帳密登入，即可進入 [sandbox](https://sandbox-pay.line.me/zh_TW/main) 環境
3.  在 sandbox 環境下可以取得金鑰
    -   金鑰取得頁面
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/483c66f3-a48a-4d43-868f-2466ed085174/Untitled.png)
        

### 使用的 Node 套件

-   Axios - 發出請求使用
-   dotenv - 取得環境變數
-   crypto-js - 加密方法

### 付款流程（PC）

1.  本地伺服器建立訂單，並發出 LINE Pay 請求（加密）
2.  LINE Pay 確認請求，無誤後提供付款連結，本地端網址協助轉址
3.  用戶使用 LINE App 開啟付款頁面，並確認付款
4.  LINE Pay 轉址至至本地伺服器 Confirm Url
5.  本地伺服器發出完成交易請求（加密）
6.  LINE Pay 確認付款，轉址至本地伺服器完成交易請求
7.  本地伺服器顯示交易完成介面

## 開發流程

1.  建立 Express 環境
2.  加入環境變數、模擬訂單資料
    -   環境變數解說
        
        ```
        # 商店 ID
        LINEPAY_CHANNEL_ID=
        
        # 商店密鑰（不可外流） 
        LINEPAY_CHANNEL_SECRET_KEY=
        
        # API 版本
        LINEPAY_VERSION=v3
        
        # LINE Pay 站點，以下為測試機位置
        LINEPAY_SITE=https://sandbox-api-pay.line.me
        
        # 金流轉址位置，可用本地端
        LINEPAY_RETURN_HOST=
        
        # 金流確認的 Router
        LINEPAY_RETURN_CONFIRM_URL=
        
        # 金流取消的 Router
        LINEPAY_RETURN_CANCEL_URL=
        ```
        
    -   模擬訂單[資料結構](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW)
        
3.  製作訂單發出請求頁面 ‘checkout’
4.  **製作發出 LINE Pay 請求 API**
    1.  加密方法：[](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW)[https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW) (****API Authentication****)
    2.  API 連結：[](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW)[https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW) (****Request API****)
    3.  Crypto 文件：[](https://www.npmjs.com/package/crypto-js)[https://www.npmjs.com/package/crypto-js](https://www.npmjs.com/package/crypto-js)
5.  製作訂單確認 API Router（與前述方法接近
    1.  API：****Confirm API****
6.  製作完成頁面

加密方法

[](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW)[https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW](https://pay.line.me/tw/developers/apis/onlineApis?locale=zh_TW)