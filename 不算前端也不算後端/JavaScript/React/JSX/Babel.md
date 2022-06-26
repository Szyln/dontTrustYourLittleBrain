---
title: "Babel"
tag: 
- js/react/jsx
- webpack
---
## Babel
>[Babel](https://babeljs.io/)

- JavaScript [[Compiler]]，可以將 [[JSX]] 編譯成原始的 React 寫法
- 可以讓你寫最新的語法
- [Vite](Vite.md), Create-React-App 都會幫你直接裝好，[webpack（未完成）](webpack（未完成）.md) 要自己裝


### 安裝 Babel
[Babel 安裝導引](https://babeljs.io/setup) --> webpack

```sh
npm install --save-dev babel-loader @babel/core
```

```js
{
	// 新增到 config 中的對應位置
  module: {
    rules: [
      {
				// 如果有除了 .js 之外的檔案的話就新增到這裡
				// 很多種副檔名的話可以這樣：test: /\.(js|mjs|ts|tsx)$/,
        test: /\.m?js$/,
				// 除外
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
					// babel 的 option 可以直接移到 ./babel.config.json 中
          options: {
						// 這個需要再安裝
            presets: ['@babel/preset-env']
          }
        }
      }
    ]
  }
}
```
再安裝 `preset-env`
```shell
npm install @babel/preset-env --save-dev
```

```json
// ./babel.config.json
{
  "presets": ["@babel/preset-env"]
}
```
#js/react/jsx 