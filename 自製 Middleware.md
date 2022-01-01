# 自製 Middleware
- Middleware 使用 req 參數
- Middleware 使用 res.send
```js
// middleware function 的參數有請求物件、回應物件、跟下一個 middleware 
app.use(function (req, res, next) {
  console.log('I am middleware');
  next();		// 有這個才會執行下一個 middleware
})

app.use(function (req, res, next) {
  console.log('I am second middleware');
  next();
})
```

## 使用 req
詳細之後會談
```js
app.use(function (req, res, next) {
	req.method = "POST";	// 把對方的請求強制改成 post
  next();
})
```

## res.send
大型專案很實用的功能，可以在還沒有 [[Routing]] 的情況下 send
```js
app.use(function (req, res, next) {
	res.send('Middleware');
  next();
})

app.get('/', (req, res) => {
	res.send('homepage');
})

// 網頁顯示會出錯
// 終端：Cannat set headers after they are sent to the client（res.send 不能送兩次）
```

## 指定特定 Route 才能使用的 Middleware
跟 [[Routing]] 的功能類似，也可以限定使用
```js
app.use('/student', (req, res, next) => {
	res.send('Middleware');
  next();
})

app.get('/', (req, res) => {
	res.send('homepage');
})

// 網頁顯示會出錯
// 終端：Cannat set headers after they are sent to the client（res.send 不能送兩次）
```

#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 