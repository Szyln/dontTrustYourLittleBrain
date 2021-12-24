#### body-parser
```js
const bodyParser = require("body-parser");

// middleware 收到請求一定會被執行
app.use(bodyParser.urlencoded(
	{ extended: true }
)});
```
#js #expressJs #node #npm #form #server #routing #module 