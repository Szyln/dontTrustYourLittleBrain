---
title: "webpack（未完成）"
tag: 
- progress
- js/webpack
- js/module
---
# webpack（未完成）
>[Gulp & Webpack 基本](https://qiita.com/annaaida/items/f2c372000e8358ea8d8f)
>[【前端速成】Webpack5 快速入門｜Tiktok 工程師帶你入門前端｜布魯斯前端](https://youtu.be/uP6KTupfyIw)


- [webpack Get Started](webpack%20Get%20Started.md)


## 目錄
- [安裝](安裝.md)

## 為什麼要用 webpack
- 現行有很多[Library 跟 Framework](Library%20跟%20Framework.md)，每個都有自己的邏輯，都有自己的 CLI（打包工具），導致每學一個框架就要換一個打包工具。
- webpack 統一上述的打包規則，可以將他們通通都編譯出來
	- 編譯 JSX（[Babel](Babel.md)）
- 搭配 plugin 做到更多事
	- 整合語法相容性：加 prefix，不擔心用新的語法寫，舊的瀏覽器不相容
- 程式碼壓縮
- 整理、最佳化模組內容


## 資料夾結構
```shell
project
|- src/
|- npm 相關的
|- index.html # 引入 bundle.js
```

## scripts
>[npm 建置與指令](npm%20建置與指令.md)

```json
"scripts": {
	"build": "webpack"
}
```

### build 
#### 指令
> 也可以到 package.json 中新增 scripts 更改
```shell
webpack
```
#### 行為
從入口檔案（預設是 `src/index.js`）開始，使用到的所有 JS 模組都打包成一個 JS 檔案（預設是`dist/main.js`）

### watch
#### 行為
`watch` 可以即時顯示更新過後的程式碼在網頁上渲染的結果
每次執行只會 `build` 跟上次執行時不一一樣的部分
### serve
```shell
webpack serve
```
開一個 `localost`


## config 設置
主要要設置的內容如下：
- **Entry**：入口檔案
- **Output**：dist
- **Loaders**：辨識 `import` 的檔案是什麼（js, css, 還是其他 asset）
- **Plugins**：除了讀檔案之外的事情
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

### devServer 設定
>- [path](path.md)

```js
// webpack.config.js

const path = require('path');

module.exports = {
	// 省略其他設定
	devServer: {
		// path.join()：將參數串起來，可以串很多個。
		contentBase: path.join(__dirname, 'public')	
	}
};
```


Webpackとは、CSSやJavaScript、画像など**Webコンテンツを構成するあらゆるファイル(アセット)を「モジュール」**という単位で取り扱い**「バンドル」という１つのファイルに最適な形で変換する**ためのツールです。（バンドルとは複数ファイルを1 枚のファイルにまとめること）

・機能ごとにファイルを分割（モジュール化）する開発ができるから  
・ジュール（npmなどでインストールできるパッケージなど）も利用できるから  
・リクエスト数を減らせるから  
・依存関係を解決したファイルを出力できるから



- `Loaders` 將圖像、CSS 等 JS 之外的檔案作為 JS 讀取，在 bundle 前的動作。画像やCSSなどの**JavaScript 以外のファイルをJavaScriptで扱えるように変換**したり、バンドルする前にモジュールに対して実行する機能のこと。TypeScriptをJavaScriptに変換、画像をDataURLに変換、コードをチェックするなど、ローダーによって機能は様々。
	- TS -> JS
	- 圖像 -> DataURL
	- 檢查程式碼等

- `Plugins` モジュールのバンドル時に実行される様々な処理。バンドル時にやりたい処理を呼び出す。

- `resolve` 特定の処理の指定、定義するやつ

- `Browser Compatibility` （どのブラウザに対応するか）

## env
Node.jsの環境変数は、process.envというオブジェクトに格納されます。  
環境変数というのは、アプリケーションを動作させる際の最も基本的な設定内容が入った箱のようなものです。

productionを指定すると本番環境を意味します。  
developmentを指定すると開発環境を意味します。  
指定した内容に基づいた環境設定の動作を反映させることができます。

## webpack-dev-serverとは

簡易的にサーバーを立ち上げつつ「webpack」コマンドを実行してくれるもの

## watchモード

### [](https://qiita.com/annaaida/items/f2c372000e8358ea8d8f#npm-run-watch%E3%81%A8%E3%81%AF)npm run watchとは

開発用のコマンドで、ファイルの変更を監視してブラウザに自動的に反映してくれる

### [](https://qiita.com/annaaida/items/f2c372000e8358ea8d8f#npm-run-build%E3%81%A8%E3%81%AF)npm run buildとは

本番公開用のコマンドで、トランスパイルされ圧縮をして「public」フォルダに吐き出す


https://goworkship.com/magazine/how-to-webpack/
![](https://i0.wp.com/goworkship.com/magazine/app/uploads/2018/09/before-2.png?resize=840%2C473&ssl=1)

