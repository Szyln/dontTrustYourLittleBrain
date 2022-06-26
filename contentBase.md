#### contentBase
>- 目前結構：`index.html` 在 `dist` 裡面

想要檢視 output 結果，指令 `webpack`，如果要到網頁首頁的話網址會是
```
localhost:3000/dist/
```
如果想要網頁首頁的的路徑為
```
localhost:3000/
```
那就要使用 `contentBase` 這個設定，這樣就會指定 dist 資料夾為網址的起點了
>- [path](path.md)`.join()`：將參數串起來，可以串很多個（需匯入 `path` 模組）
```js
// webpack.config.js
const path = require('path');
module.exports = {
	devServer: {		
			contentBase: path.join(__dirname, 'dist')	
		}
};
```