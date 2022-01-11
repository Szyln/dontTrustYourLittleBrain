# cookie-session
[npm](https://www.npmjs.com/package/cookie-session)
```
npm i cookie-session
```

## 建置

```js
const cookieSession = require('cookie-session');
```

### middleware
>[[指定特定 Route 才能使用的 Middleware]]
```js
// 在特定 route 使用的 middleware 之前
app.use(cookieSession({
  name: 'session',
  keys: [process.env.SECRET],

  // Cookie Options
  maxAge: 24 * 60 * 60 * 1000 // 24 hours
}))
```
>[[passport-google-oauth20 的 .env 變數]]