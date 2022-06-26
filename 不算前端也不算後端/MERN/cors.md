---
title: "cors"
tag: 

- js/mern
---
## cors
>[npm](https://www.npmjs.com/package/cors)

前後端可以同時一起跑不同 server 

### 裝在 server
```shell
npm i cors
```
### 後端設定
```js
const cors = require('cors');

// middleware(routing 的 middleware 之前)
app.use(cors())

#js/mern 