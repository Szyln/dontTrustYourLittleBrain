## 即時預覽：webpack-dev-server
>- [Using webpack-dev-server](https://webpack.js.org/guides/development/#using-webpack-dev-server)

```sh
npm install --save-dev webpack-dev-server
```

```js
module.exports = {
	devServer: {
		static: './dist',
	},
	optiomization: {
		runtimeChunk: single,
	}
}
```