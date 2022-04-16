## SASS 設定
建議的 sass-loader： [[dart-sass(sass) 建置]]

```shell
npm install sass-loader sass webpack --save-dev
```
```js
rules: [
	{
		test: /\.css$/i,
		// css 設定中再 chain 一個 'sass-loader'
		use: ['style-loader', 'css-loader', 'sass-loader'],
	},
]
```

