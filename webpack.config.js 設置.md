## config 設置
主要要設置的內容如下：

- **Entry**：入口檔案
- [Output](Output.md)：dist
- [Loaders](Loaders.md)：將 JS 之外的 asset 做為 JS module 來匯入
- [[Plugins]]：打包時執行的動作，可自己添加需要的外掛
	- bundle 前清空 dist
- **Mode**：指定 development, production, none 模式
- Browser Capability

>- [path](path.md)


```js
// webpack.config.js

// output.path 需要使用絕對路徑，先匯入 path 模組
const path = require('path');

module.exports = {
  // mode：v4 之後不指定會跳提示
	// 可以指定的有：development, production, none
  mode: 'development',
  // entry point，從這個檔案開始分析模組的依存關係
  entry: './src/js/app.js',
  // 輸出的設定
  output: {
    // 打包後的檔案名稱
    filename: 'main.bundle.js',
    // 輸出路徑：必須使用絕對路徑
    path: path.join(__dirname, 'dist')
  }
};
```



