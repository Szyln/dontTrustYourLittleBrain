---
title: "webpack"
tag: 
- progress
- js/webpack
- js/module
---
## webpack
>- [Gulp & Webpack 基本](https://qiita.com/annaaida/items/f2c372000e8358ea8d8f)
>- [【前端速成】Webpack5 快速入門｜Tiktok 工程師帶你入門前端｜布魯斯前端](https://youtu.be/uP6KTupfyIw)


- [webpack Get Started](webpack%20Get%20Started.md)


## 目錄
- [安裝](安裝.md)
- [為什麼要用 webpack](為什麼要用%20webpack.md)
- [webpack 的 scripts](webpack%20的%20scripts.md)
- [webpack.config.js 設置](webpack.config.js%20設置.md)

### Loaders
- [Loaders](Loaders.md)：讀取、辨識任何 asset, js, css, html 的工具 ^57cd18
	- [webpack 讀取 css](webpack%20讀取%20css.md)
	- [webpack 使用 dart-sass](webpack%20使用%20dart-sass.md)
	- [webpack 使用圖檔及其他 Asset：Asset Modules](webpack%20使用圖檔及其他%20Asset：Asset%20Modules.md)
	- [安裝 Babel](安裝%20Babel.md)

### Plugins
- [Plugins](Plugins.md) ^0f7254
	- [生成 Output 的 HTML 結果：HtmlWebpackPlugin](生成%20Output%20的%20HTML%20結果：HtmlWebpackPlugin.md)
	- [生成 Output 的 CSS 結果：MiniCssExtractPlugin](生成%20Output%20的%20CSS%20結果：MiniCssExtractPlugin.md)

### Output
- [Output](Output.md) ^1f8c0b
	- [避免因既存的快取，更新後抓不到新內容：對 filename hash](避免因既存的快取，更新後抓不到新內容：對%20filename%20hash.md)
	- [清除 Output 內容：clean](清除%20Output%20內容：clean.md)

### 其他設定
- [devServer](devServer.md)
- [讓 devtool 更好讀：source-map](讓%20devtool%20更好讀：source-map.md)


### 開發工具
像是 live server 的工具，開發時可以即時檢視更新
- [即時預覽：webpack-dev-server](即時預覽：webpack-dev-server.md)

> 還有其他方法
>- webpack's [Watch Mode](https://webpack.js.org/configuration/watch/#watch)：需要重整
>- [webpack-dev-middleware](https://github.com/webpack/webpack-dev-middleware)





## 資料夾結構
```shell
project
|- src/
|- npm 相關的
|- index.html # 引入 bundle.js
```






https://goworkship.com/magazine/how-to-webpack/
![](https://i0.wp.com/goworkship.com/magazine/app/uploads/2018/09/before-2.png?resize=840%2C473&ssl=1)

