---
title: "ESLint"
tag: 
- 
---
## ESLint
> [reactjs-tutorial: linting](https://code.visualstudio.com/docs/nodejs/reactjs-tutorial#_linting)
## 設定
### 安裝 ESLint (npm)
```shell
npm install -g eslint # 全域
```
### 初始化
初始化會在終端機有以下問題要回答
```shell
eslint --init # 或是 shift + cmd + P 輸入 create eslint configuration
```
>引用[Day02 | 整齊的程式，讓看的人長命百歲，給我用 ESLint](https://ithelp.ithome.com.tw/articles/10215259)
>
>如果下載的 ESLint 的版本是 `@5.16.0`，那問題大概會是：
>1.  你想使用 ESLint 來做什麼？  
>    選擇第三個：檢查語法、找出問題和強制執行編碼風格。
>2.  該專案是用什麼方式導入模組？  
>    選擇第一個：使用 `import/export`，之後會需要配合 Babel 和 React。
>3.  在專案裡用了哪個框架？  
>    選擇第一個：必須是 React。
>4.  想在哪個執行環境下使用？  
>    選擇第一個：Browser 瀏覽器環境。
>5.  該如何定義專案中的編碼風格？  
>    選擇第一個：依照目前流行的編碼規範。
>6.  目前流行的有三個，請問選擇哪一種？  
>    筆者習慣選擇 Airbnb，但其實三種都可以，不習慣的規則之後也能夠做例外處理。
>7.  產生的 config 檔案要用哪種格式？  
>    一樣是筆者習慣，選擇 JavaScript，看起來比較順眼。
		
### 安裝 ESLint 插件（VS code）
![](https://code.visualstudio.com/assets/docs/nodejs/reactjs/eslint-extension.png)

### React hooks 設定
>[eslint-plugin-react-hooks](React/Hook/eslint-plugin-react-hooks.md)


### 還沒仔細看的
>[ESLint - Lint工具的後起之秀](https://eyesofkids.gitbooks.io/react-basic-zh-tw/content/day03_eslint/)


## 建立規則
>[ESLint Rules](https://eslint.org/docs/rules/)
```js
 "rules": {
        "no-extra-semi":"error"
    }
```

## 修正
```shell
eslint filePath --fix
```