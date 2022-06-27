## 用 env 控制 mode
有很多種寫法，舉例用終端機指令控制：
```json
"script": {
	"build": "NODE_ENV=production webpack",
}
```

```js
const modeEnv = process.env.NODE_ENV

module.export = {
	mode: modeEnv,
}
```