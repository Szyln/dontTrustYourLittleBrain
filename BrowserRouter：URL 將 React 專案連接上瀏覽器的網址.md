---
title: "BrowserRouter：URL 將 React 專案連接上瀏覽器的網址"
tag: 
- js/react 
- js/module/npm
- routing 
---

##  BrowserRouter：URL 將 React 專案連接上瀏覽器的網址
```jsx
// main.jsx(負責 render)
// 匯入 React, ReactDOM, App
import { BrowserRouter } from 'react-router-dom'

ReactDOM.render(
  <React.StrictMode>
    {/* 用 BrowserRouter 包住 */}
    <BrowserRouter>
      {/* App 元件內為整個頁面，包含共同區塊 Nav, Footer */}
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```