# profile-route
>[[Authenticate Requests]]

[[登入後]] 會顯示 profile.ejs 頁面

>[[登入前後頁面的變化]]
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
>[[res.redirect()]]
>[[req.isAuthenticated()]]
```js
// routes/profile-route.js
const router = require('express').Router();

// 只給特定 route 用的 middleware 
const authCheck = (req, res, next) => {
	if(!req.isAUthenticated) {
		res.redirect('/auth/login');
	} else {
		next();
	}
}

// google login
// 使用 req.user
// /profile 請求中，客戶端會先經過 authCheck
// 如果尚未認證會導去登入畫面，有的話就會執行這個 route
// render porfile 頁面
router.get('/', authCheck, (req, res) => {
	res.render('profile', { user: req.user });
})
```

```js
route.get('/post', authCheck, (req, res) => {
	res.render('post', { user: req.user });
})
export.modules = router;
```
>[[Routing 執行時的 Middleware（Route 中間）]]

#passport #oauth #authentication #expressJs