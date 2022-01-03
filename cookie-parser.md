[npm](https://www.npmjs.com/package/cookie-parser)

---

```
$ npm install cookie-parser
```

```js
const cookieParser = require('cookie-parser')
```

```js
const express = require('express')
const cookieParser = require('cookie-parser')
const app = express()

app.use(cookieParser())

app.get('/', function (req, res) {
  // Cookies that have not been signed
  console.log('Cookies: ', req.cookies)

  // Cookies that have been signed
  console.log('Signed Cookies: ', req.signedCookies)
})

app.listen(8080)

// curl command that sends an HTTP request with two cookies
// curl http://127.0.0.1:8080 --cookie "Cho=Kim;Greet=Hello"
```