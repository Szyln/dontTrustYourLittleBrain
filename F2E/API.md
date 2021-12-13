# API
[API 是什麼，能吃嗎？](https://hackmd.io/NnnTQ3gLQIagIsqsp9CiQQ)

資料庫的接口

[應用程式介面（英語：Application Programming Interface）](https://zh.wikipedia.org/wiki/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E6%8E%A5%E5%8F%A3)

API 提供 JSON
我們進行 request 請求（求一個JSON資料回來

-   [Web API：TDX 觀光 API](https://tdx.transportdata.tw/api-service/swagger)
    -   我想獲得台灣觀光景點資料
    -   我輸入說明文件上的[網址請求](https://ptx.transportdata.tw/MOTC/v2/Tourism/ScenicSpot?$top=30&$format=JSON)方式
    -   TDX 伺服器回應我對應的 JSON 格式資料
    -   [範例 Code](https://codepen.io/hexschool/pen/dyRjQRW?editors=1010)

```
let data;


axios.get('https://ptx.transportdata.tw/MOTC/v2/Tourism/ScenicSpot?$top=30&$format=JSON').then(function(res){
  let data = res.data;
  console.log(data); 
  document.querySelector('.container').innerHTML = `
 <h1>${data[0].Name}</h1>
 <img src="${data[0].Picture.PictureUrl1}">` 
})

```

API資料沒有提供修改權限的話，前端是動不了的

#js #api