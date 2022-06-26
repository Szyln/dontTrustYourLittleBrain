## scripts
>[npm 建置與指令](npm%20建置與指令.md)

```json
"scripts": {
	"build": "webpack"
}
```

### build 
從入口檔案（預設是 `src/index.js`）開始，使用到的所有 JS 模組都打包成一個 JS 檔案（預設是`dist/main.js`）

> 也可以到 package.json 中新增 scripts 自訂 `"build": "webpack"`
```shell
webpack
```
> 第一次執行會需要安裝 webpack-dev-server （會自動跳出提示）

### serve
開一個 `localost`

```shell
webpack serve
```


### watch
`watch` 可以即時顯示更新過後的程式碼在網頁上渲染的結果
每次執行只會 `build` 跟上次執行時不一一樣的部分
