---
title: "Plugins"
tag: 
- webpack
---

##  Plugins
```js
// plugin 要匯入
module.exports = {
	plugins: [
		// 
		new PLUGIN1(),
		new PLUGIN2(),
	]
}
```
- bundle 前清空 dist
- [生成 Output 的 HTML 結果：HtmlWebpackPlugin](生成%20Output%20的%20HTML%20結果：HtmlWebpackPlugin.md)
- [生成 Output 的 CSS 結果：MiniCssExtractPlugin](生成%20Output%20的%20CSS%20結果：MiniCssExtractPlugin.md)