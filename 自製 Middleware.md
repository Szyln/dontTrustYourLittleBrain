# 自製 Middleware
- [[Middleware 使用 req 參數]]
- [[Middleware 使用 res.send]]
- [[指定特定 Route 才能使用的 Middleware]]
- [[Middleware 的位置]]
	- [[Routing 中間使用 Middleware]]
- [[Error Handling（Routing 後面）]]
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







#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 