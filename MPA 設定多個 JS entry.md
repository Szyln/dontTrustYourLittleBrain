## MPA 設定多個 JS entry
```js
module.exports = {
  //...
  entry: {
    home: './home.js',
    about: './about.js',
    contact: './contact.js',
  },
};
```

> [SPA](SPA.md) 並不需要這樣設定