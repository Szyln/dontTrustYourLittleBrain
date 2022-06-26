## 為什麼要用 webpack
- 現行有很多[Library 跟 Framework](Library%20跟%20Framework.md)，每個都有自己的邏輯，都有自己的 CLI（打包工具），導致每學一個框架就要換一個打包工具。
- webpack 統一上述的打包規則，可以將他們通通都編譯出來
	- 編譯 JSX（[Babel](Babel.md)）
- 搭配 plugin 做到更多事
	- 整合語法相容性：加 prefix，不擔心用新的語法寫，舊的瀏覽器不相容
- 程式碼壓縮
- 整理、最佳化模組內容

Webpack 將所有的元素（CSS, JS, 圖像等檔案（asset））當作一個一個的模組，並將他們打包（bundle）成一個檔案。

特性如下：
- 開發時所有的功能都可以分開處理（模組化）
- 可以使用像是 npm 來源的 module
- 減少 request 次數
- 打包不用擔心檔案間的依存關係