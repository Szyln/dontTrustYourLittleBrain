# Module Wrapper
[21/11/12 現下的 Document 說明](https://nodejs.org/dist/latest-v17.x/docs/api/modules.html#the-module-wrapper)

JS 可以在瀏覽器內直接執行，但透過 Node 在終端運行時，會用 Module Wrapper 將 js 程式碼包起來再運行

```js
(function(exports, require, module, __filename, __dirname) {
	// Module code actually lives in here
});
```

所以會使全域變數都會限制在這個函式的作用域([[Scope#Function Scope]])內

## Node.js 的預設參數
[[Module Wrapper]] 帶有幾個參數可以使用，平常在瀏覽器運作時是不會有這些參數的

## 位置相關
- 文件位置：`__filename`
- 資料夾位置：`__dirname`

### [[取得 Node.js 裡的模組]] 相關
- export：[[匯出模組]]
- require：[[匯入模組]]
- module：[[module 參數]]

> [[整合模組匯出匯入]]：進階的匯出匯入使用法

## 使用方式
[[send 和 sendFile 回應(express)#res sendFile]]
```js
app.get("/", (req, res) =>{
	res.sendFile(__dirname + "/index.html"))
})
```
使用 `path` 模組 要用 [[join()]]
```js
// 除了 express, app 之外匯入要多匯入這個
const path = reqire("path");

// 用 path.join，網址路徑不用寫成 /index.html
app.get("/", (req, res) =>{
	res.sendFile(path.join(__dirname, "index.html"))
})
```

#js #advanceJs #library #framework #nodeJs #backEnd #module 