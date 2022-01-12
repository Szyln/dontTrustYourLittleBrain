# profile-route
[[auth-route#用戶登入後]] 會顯示 profile.ejs 頁面
## middleware
`/profile` 的路徑會先執行 profile-route
```js
// index.js
const profileRoute = require('./routes/profile-route');
const authCheck = (req, res, next) => {
	if(!req.isAUthenticated)
}

// middleware
app.use('/profile', profileRoute);
```


```js
// routes/profile-route.js

const router = require('express').Router();

router.get('/', (req, res) => {
	res.render('profile');
})

export.modules = router;
```

