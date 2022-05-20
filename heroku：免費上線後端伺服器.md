---
title: "heroku：免費上線後端伺服器"
tag: 
- 
---

##  heroku：免費上線後端伺服器
>- [Heroku 免費部署PHP網站，申請、安裝、使用全攻略](https://www.minwt.com/website/server/21883.html)

### 免費版的限制
>引用：[讓免費的heroku永不休眠](https://blog.typeart.cc/%E8%AE%93%E5%85%8D%E8%B2%BB%E7%9A%84heroku%E6%B0%B8%E4%B8%8D%E4%BC%91%E7%9C%A0/)
>
>- 依照 dyno 的運行時間計費。本身提供了 550 小時的額度。通過信用卡認證後則高達 1000 小時。一個月算 31 天，且 24 小時醒著也頂多 744 小時，完全足夠使用！
>- 資料庫免費限制 1 萬筆，最多 20 個同時連線
>- 半小時內若無人使用的話，APP 會自動進入 休眠狀態。當有人造訪網站時，則需要等待 20 秒左右啟動系統。若是架來 DEMO 或自用的小服務，使用體驗就差了


### 第一次建置
- [Node](Node.md)
- [Git](Git.md)
- 註冊 Heroku
- 安裝 heroku CLI(command line interface)

```shell
npm install -g heroku
```

### 專案上線
- [[git]] 要 [git commit](git%20commit.md) 完成

```shell
heroku login
```

```shell
heroku create
```

```shell
git push heroku master
```

```shell
heroku open
```