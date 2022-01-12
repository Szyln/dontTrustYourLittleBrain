# profile-route
[[auth-route#用戶登入後]] 會顯示 profile.ejs 頁面
## middleware
`/profile` 的路徑會先執行 profile-route 模組
```js
// index.js
const profileRoute = require('./routes/profile-route');

// middleware
app.use('/profile', profileRoute);
```

## profile-route
```js
// routes/profile-route.js
const router = require('express').Router();

// 只給特定route 用的 middleware 
const authCheck = (req, res, next) => {
	if(!req.isAUthenticated)
}


router.get('/', (req, res) => {
	res.render('profile');
})

export.modules = router;
```
>[[指定特定 Route 之前的 Middleware（Route 前面）]]
