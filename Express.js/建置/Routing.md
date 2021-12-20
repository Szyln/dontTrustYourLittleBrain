# Routing(Express)
路徑的意思，後端處理網路請求時，不同路徑要給不同的內容
- [[Routing#Routing for all 回應亂打的網址]]
- [[Routing#Routing for pattern 回應有規律的網址]]
- [[回應表單 (Routing for Query)]]


## Request Handling
處理各種網路請求的內容
```js
// Express 的寫法
app.get('/', function (req, res) {	// 參數：網址，建立 server
	res.send('Hello World')			// 顯示文字
})
```
可以設定不同的網址不同反應
```js
// Express 的寫法
app.get('/', function (req, res) {			// 
	res.send('home page')					// 
})

app.get('/product', function (req, res) {	// 不同網址
	res.send('product page')				// 
})
```

## Routing for all 回應亂打的網址
這個要放在 [[Routing#Request Handling]] 的最後面，才不會什麼網址都跑這個
```js
app.get('*', (req, res) => {
	res.send('頁面不存在');
})
```
- [[404 Not Found]]


## Routing for pattern 回應有規律的網址
網址尾端內容，如果是想要顯示有規律的內容（例如搜尋結果）
可以在網址尾端加入 `/:不特定內容的群組`
```js
app.get('/某個分支頁面/:分支底下的特定內容', (req, res) => {
	res.send('你要找的是' + res.params.分支底下的特定內容 + '嗎？');
})
```
#### 舉例
搜尋就可以搜不同的內容，網頁上都會顯示同樣的格式
```js
app.get('/search/:result', (req, res) => {
	res.send('你要找的是' + res.params.result + '嗎？');
})
```

>[[從物件中提取屬性到變數中 Destructing an object]] 提到可以把物件內容提取出來，增加易讀性
>```js
>app.get('/search/:result', (req, res) => {
>	let { result } = res.params;
>	res.send('你要找的是' + result + '嗎？');
>})
>```
## Routing for Query 回應表單
[[回應表單 (Routing for Query)]]


#js #npm #node #expressJs #server #routing 