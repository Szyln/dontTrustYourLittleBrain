## webpack 使用 dart-sass
>建議的 sass-loader： [[dart-sass(sass) 建置]]

webpack 本身無法讀取 JS 以外的內容，要讀取 css 必須安裝必要的 [Loaders](Loaders.md)

>[[webpack 讀取 css]]

```shell
npm install sass-loader sass webpack --save-dev
```

### config 中加入
```js
rules: [
	{
		test: /\.css$/i,
		// css 設定中再 chain 一個 'sass-loader'
		use: ['style-loader', 'css-loader', 'sass-loader'],
	},
]
```