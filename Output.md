## Output
```js
// 匯入 path 模組
module.exports = {
	output: {
		// 打包後的檔案名稱
		filemane: 'main.bundle.js',
		// 輸出路徑：必須使用絕對路徑
		path: path.join(__dirname, 'dist'),
	}
}
```

- [避免因既存的快取，更新後抓不到新內容](避免因既存的快取，更新後抓不到新內容.md)