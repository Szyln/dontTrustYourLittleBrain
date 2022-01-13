## 匯入(auth-route)
```js
// local login, oauth
const router = require('express').Router();
const passport = require('passport');
// 註冊加密用： bcrypt
const bcrypt = require('bcrypt');
// 
const session = require('express-session');
const flash = require('connect-flash');
```
>[[bcrypt]]
>[[express-session]]
>[[connect-flash]]