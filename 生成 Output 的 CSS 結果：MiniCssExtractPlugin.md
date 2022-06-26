---
title: "生成 Output 的 CSS 結果：MiniCssExtractPlugin"
tag: 
- webpack
---

##  生成 Output 的 CSS 結果：MiniCssExtractPlugin
>- [MiniCssExtractPlugin](https://webpack.js.org/plugins/mini-css-extract-plugin/#root)

- [webpack 讀取 css](webpack%20讀取%20css.md) 的 `style-loader` 打包會直接打到 html 檔案的 `style` 標籤內
- `MiniCssExtractPlugin` 可以將 css 在 [Output](Output.md) 中獨立開來
- 

```shell
npm install --save-dev mini-css-extract-plugin
```

```js
const MiniCssExtractPlugin = require("mini-css-extract-plugin");

module.exports = {
  plugins: [new MiniCssExtractPlugin()],
  module: {
    rules: [
      {
        test: /\.css$/i,
				// 新增這個 plugin
        use: [MiniCssExtractPlugin.loader, "css-loader"],
      },
    ],
  },
};
```

### 參數
#### filename
>[避免因既存的快取，更新後抓不到新內容：對 filename hash](避免因既存的快取，更新後抓不到新內容：對%20filename%20hash.md)

同樣因快取的問題，CSS 也是要這樣處理
```js
plugins: [new MiniCssExtractPlugin({
	filename: 'main.[hash].css'
})],
```


>[webpack 讀取 css](webpack%20讀取%20css.md)