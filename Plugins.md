---
title: "Plugins"
tag: 
- webpack
---

##  Plugins

- bundle 前清空 dist


## HtmlWebpackPlugin
>[HtmlWebpackPlugin](https://webpack.js.org/plugins/html-webpack-plugin/#root)

```shell
npm install --save-dev html-webpack-plugin
```

```js

const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  plugins: [new HtmlWebpackPlugin()],
};

```

### 更多參數
>- [option](https://github.com/jantimon/html-webpack-plugin#options)

```js
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  plugins: [new HtmlWebpackPlugin({
		template: './index.html'
	})],
};
```