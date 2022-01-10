# profile-route
[[auth-route]] 
```js
// index.js
const profileRoute = require('./routes/profile-route');


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

