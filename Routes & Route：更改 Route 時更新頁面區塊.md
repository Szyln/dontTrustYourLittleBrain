---
title: "Routes & Route：更改 Route 時更新頁面區塊"
tag: 
- js/react 
- js/module/npm
- routing 
---

##  Routes & Route：更改 Route 時更新頁面區塊
>情境：頁面上 Header, Footer 固定，只對 main 區塊進行渲染（不需每一個頁面都重寫一次 Header, Footer）

`<Route />` 
- `path`（路徑）
- `element`（頁面.jsx）
```jsx
// 匯入 React, Nav, HomePage, About, Footer
import { Routes, Route } from 'react-router-dom'

function App() {
  return (
    <>
      <Nav />
      {/* 使用 Routes 包住 Route */}
      <Routes>
				{/* Route 決定點連結之後會產生的內容 */}
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<About />} />
      </Routes>
      <Footer />
    </>
  );
}
export default App;
```




>[[Nested Routes]]