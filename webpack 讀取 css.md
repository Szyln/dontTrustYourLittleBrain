---
title: "webpack 讀取 css"
tag: 
- webpack
---

##  webpack 讀取 css
webpack 本身無法讀取 JS 以外的東西，需要載入 [Loaders](Loaders.md) 來處理 css

>[webpack 使用 dart-sass](webpack%20使用%20dart-sass.md)

```shell
npm i --save-dev css-loader style-loader
```

```js
// webpack.config.js

module.exports = {
	module: {
		rules: [
			{
				test: /\.css$/i,
				use: ['style-loader', 'css-loader'],
			},
		],
	},
};
```

### 結果
這樣在寫專案的樣式的時候，就可以把 css 檔案像是 JS 模組一樣匯入做使用了
```jsx
import css from 'style.css'
```