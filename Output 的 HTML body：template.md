#### Output 的 HTML body：template
指定 output 中的 `index.html` 的原始樣本，取得 `body` 內容
```js
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  plugins: [new HtmlWebpackPlugin({
		// 這個檔案不是最終 build 的檔案
		template: './index.html'
	})],
};
```