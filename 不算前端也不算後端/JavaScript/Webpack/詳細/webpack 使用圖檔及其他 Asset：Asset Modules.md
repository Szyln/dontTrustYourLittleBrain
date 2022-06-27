## webpack 使用圖檔及其他 Asset：Asset Modules
>- [Asset Modules](https://webpack.js.org/guides/asset-modules/#root)

除了 JS, CSS, HTML 還有其他 asset，像是圖檔
```js
module.exports = {
	module: {
		rules: [
			{
				// 讓 webpack 讀取這些格式
				test: /\.(png|jpg|gif)$/i,
				type: 'asset/resource'
			}		
		]
	}
}
```