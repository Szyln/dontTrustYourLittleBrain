---
title: "避免因既存的快取，更新後抓不到新內容：對 filename hash"
tag: 
- webpack
---

##  避免因既存的快取，更新後抓不到新內容：對 filename hash
>[Hash Function](Hash%20Function.md)：加密

設定 [[Output]].filename 加入 hash 處理，這樣每次 build 的時候就會產生不同名稱的檔案，迫使每次更新後，用戶都需要讀取不同的檔案，避免一直讀到舊的內容

![](https://i.imgur.com/oPxsGof.png)
如圖

```js
module.exports = {
	output: {
		filename: 'main.[hash].bundle.js'
	}
}
```

> 但這樣對於 `index.html` 來說，每次要讀取的 `<script>` 都不一樣，所以需要再安裝一個 [生成 Output 的 HTML 結果：HtmlWebpackPlugin](生成%20Output%20的%20HTML%20結果：HtmlWebpackPlugin.md)，生成預期的 html output

> CSS 也需要這樣處理：[生成 Output 的 CSS 結果：MiniCssExtractPlugin](生成%20Output%20的%20CSS%20結果：MiniCssExtractPlugin.md) 也有一樣的功能