## 複數 script 時的執行環境
>TODO 與[模組](模組.md)的差異

多個 script 都會視為同一個執行環境，也就代表他們共用全域
```html
<html lang="en">
<body>
	<!-- 多個 script 都會視為同一個執行環境，也就代表他們共用全域 -->
	<!-- 程式碼順序為：app1, app2, app3  -->
  <script src="./app1.js"></script>
  <script src="./app2.js"></script>
  <script src="./app3.js"></script>
</body>
</html>
```

開發者可能就會 [將變數定義預設值](將變數定義預設值.md)，如果已經有人使用就不去使用這個變數
```js
// 檢查全域變數有沒有衝突，沒有就覆蓋
window.libraryName = window.libraryName || 'Lib 2'
```