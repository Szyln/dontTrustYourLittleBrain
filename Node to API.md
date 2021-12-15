# Node to API
[[Fetch#需要有 Authorization Key 才能使用的 API]]
[[Express.js]]
[[EJS]]
```
npm init
npm install express ejs nodemon 
(不用安裝 mongoose)
```

```js
// app.js
const express = require('express');
const app = express();
const ejs - require('ejs');

// middleware
app.use(express.static('public'));
// 這是啥
app.set('view engine', ejs);

// request handdling
app.get('/', (req, res) => {
	res.render('index.ejs')
})

app.get('/:city', (req, res) => {
	let { city } = req.params;
	res.render('weather.ejs')
})

app.listen(3000, () => {
	console.log('server is running on 3000')
})
```