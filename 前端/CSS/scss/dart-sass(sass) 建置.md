---
title: "dart-sass(sass) 建置"
tag: 
- 
---
## dart-sass (sass) 建置

>[Install Sass](https://sass-lang.com/install)
>[Sass Basics](https://sass-lang.com/guide)

###  安裝到電腦 (global)
#### npm
```shell
npm i -g sass
```
>- [其他安裝方式（brew 等）](其他安裝方式（brew%20等）.md)

### 加入到專案
#### 加入到 vite 專案

```shell
npm add -d sass # 在該專案執行
```

#### 加入到 webpack
[webpack 使用 dart-sass](webpack%20使用%20dart-sass.md)

### 使用方法
>[npm init 初始化(package.json)](後端/Node.js/模組/npm/指令/npm%20init%20初始化(package.json).md)，"script" 可以加入自訂指令

設定 `build-css` 的指令，直接輸入 `npm run build-css` 即可運行
```json
"scripts": {
	"build-css": "sass -w src/style/scss/all.scss src/style/all.css"
},
```

#### 原本的寫法是這樣
運行將 `.sass`, `.scss` 編譯成 `.css` 的指令
```shell
sass <路徑/all.scss> <路徑/all.css>
```

##### 即時監控更新 --w
每次寫新的 Sass 就要執行一次指令不太實際，可以使用 `-w` （ `--watch` 的縮寫）來執行 
```shell
sass --w <路徑/all.scss> <路徑/all.css>
```



#vite #js/react #css/scss #node/npm 