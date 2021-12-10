# Module Wrapper
[21/11/12 現下的 Document 說明](https://nodejs.org/dist/latest-v17.x/docs/api/modules.html#the-module-wrapper)

在瀏覽器與終端裡運行 JS 的不同，差異是終端需要透過 Module Wrapper 的功能，先用這個函數將 js 檔包起來運行

```js
(function(exports, require, module, __filename, __dirname) {
	// Module code actually lives in here
});
```

使全域變數都會限制在這個函式的作用域([[Scope#Function Scope]])內

## Node.js 的預設參數
在瀏覽器不會出現，會在終端出現
```js
(exports, require, module, __filename, __dirname)
```

### __filename
```js
console.log(__filename);		// 文件位置
```
可以顯示在伺服器裡的位置

### __dirname
```js
console.log(__filename);		// 文件的所在資料夾
```

#### 使用方式
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

### exports, require, module

#js #advanceJs #library #framework #nodeJs #backEnd #module 