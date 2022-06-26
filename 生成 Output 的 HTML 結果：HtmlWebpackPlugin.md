---
title: "生成 Output 的 HTML 結果：HtmlWebpackPlugin"
tag: 
- webpack
---

##  生成 [Output](Output.md) 的 HTML 結果：HtmlWebpackPlugin
>- [HtmlWebpackPlugin](https://webpack.js.org/plugins/html-webpack-plugin/#root)
>- [避免因既存的快取，更新後抓不到新內容：對 filename hash](避免因既存的快取，更新後抓不到新內容：對%20filename%20hash.md)：會導致每次要抓的 script source 都不一樣，所以 build 時要自動生成 html 來避免這個手續

```shell
npm install --save-dev html-webpack-plugin
```

[Output](Output.md) 中的 `index.html` 自動加入新的 script source（但這樣 `body` 的內容還是空的）
```js

const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  plugins: [new HtmlWebpackPlugin()],
};

```
> `./index.html` 裡面就不用再引入 script 了

### 更多參數
>- [option](https://github.com/jantimon/html-webpack-plugin#options)

- [Output 的 HTML body：template](Output%20的%20HTML%20body：template.md)
