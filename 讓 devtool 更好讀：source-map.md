## 讓 devtool 更好讀：source-map
- webpack 會將 JS 檔 bundle 起來，在 devtool 裡面很不好讀，像如果有[安裝 Babel](安裝%20Babel.md) 的話，devtool 內看原始碼（編譯前）比較好 debug
- 會在 [Output](Output.md) 會新增一個 `.js.map` 的檔案

```js
module.exports = {
	devtool: 'source-map',
}
```