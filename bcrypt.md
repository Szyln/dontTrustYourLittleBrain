# bcrypt
[npm](https://www.npmjs.com/package/bcrypt)
業界很有名拿來做 [[Salting]], [[Hash Function]] 的演算法

```js
const bcrypt = require('bcrypt');
const saltRounds = 10;				// cost factor：執行 2 的幾次方次
// const myPlaintextPassword = 's0/\/\P4$$w0rD';
// const someOtherPlaintextPassword = 'not_bacon';
```

```js
bcrypt.genSalt(saltRounds, function(err, salt) {
    bcrypt.hash(myPlaintextPassword, salt, function(err, hash) {
        // Store hash in your password DB.
    });
});
```

>[[註冊頁面]] 應該加密後再儲存
#cryptogrphy #node #npm #module 