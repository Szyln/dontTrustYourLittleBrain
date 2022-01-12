# profile-route
[[auth-route#用戶登入後]] 
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

