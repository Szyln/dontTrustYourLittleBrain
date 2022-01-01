# 自製 Middleware
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