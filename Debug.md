---
title: "ESlint"
tag: 
- js/react
- debug
---
## Debug
> [reactjs-tutorial: linting](https://code.visualstudio.com/docs/nodejs/reactjs-tutorial#_linting)

- `⇧⌘M` ：開啟 Problems 區塊
- 安裝 ESlint

### ESLint
>[ESLint - Lint工具的後起之秀](https://eyesofkids.gitbooks.io/react-basic-zh-tw/content/day03_eslint/)
>[eslint-plugin-react-hooks 也要加到設定中](https://www.npmjs.com/package/eslint-plugin-react-hooks)
>[使用 Eslint 為團隊代碼做基礎的品質把關](https://dotblogs.com.tw/wasichris/2019/12/15/185845)
>[Day02 | 整齊的程式，讓看的人長命百歲，給我用 ESLint](https://ithelp.ithome.com.tw/articles/10215259)
- Command Palette( `⇧⌘P` ) 輸入 `eslint` --> Create ESLint configuration 來生成 `.eslintrc.js` 檔案，會跳出終端機指令，詢問安裝設定，可以全部維持預設

#### 建立規則
>[ESLint Rules](https://eslint.org/docs/rules/)

```js
 "rules": {
        "no-extra-semi":"error"
    }
```
#### React
## 另一種安裝方法
```shell
$ npm install eslint --save-dev
```
```shell
$ .\node_modules\.bin\eslint --init #
```
### Debugger
>