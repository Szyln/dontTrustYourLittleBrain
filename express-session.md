# express-session
[npm](https://www.npmjs.com/package/express-session)（不要用到 express-sessions）
使用 session 的模組

```
$ npm install express-session
```

# 使用
```js
const session = require('express-session');
```

## [[Middleware(express)]]
- [[secret 的變數設定]]
```js
app.use(session({
	// 這段字串建議要放入一個全域變數裡面 
	secret: 'Should be an env variable but not for now';
	resave: false,							// 變更後要不要儲存進去（少用到）
	saveUninitaialized: false		// 沒有變更的話需不需要儲存（少用到
	
}))
```

## Routing
```js
app.get('/', (req, res) => {
	console.log(req.session);
})
```

#js #backEnd #server #storage #expressJs