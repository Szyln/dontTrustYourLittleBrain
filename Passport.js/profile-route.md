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
>[[req.user]]
```js
// routes/profile-route.js
const router = require('express').Router();

// 只給特定route 用的 middleware 
const authCheck = (req, res, next) => {
	if(!req.isAUthenticated) {
		res.redirect('/auth/login');
	} else {
		next();
	}
}

// 使用 req.user
router.get('/', authCheck, (req, res) => {
	res.render('profile', { user: req.user });
})

export.modules = router;
```
>[[Routing 執行時的 Middleware（Route 中間）]]
