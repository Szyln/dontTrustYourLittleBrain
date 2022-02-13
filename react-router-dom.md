# react-router-dom
```
npm install react-router-dom
```

- Routing
- Link (`a` 標籤)

>[[react-router-dom 版本差異]]

---

## Routing
可以在 React 操作 Routing

```jsx
// main.jsx(負責 render)
// 匯入 React, ReactDOM, App, {BrowserRouter}(react-router-dom)
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

`<Route />` 內寫入 `path`（路徑）, `element`（頁面.jsx）
```jsx
// 匯入 React, Nav, HomePage, About, Footer, {Routes, Route} (react-router-dom)
function App() {
  return (
    <>
      <Nav />
      {/* 使用 Routes 包住 Route */}
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<About />} />
      </Routes>
      <HomePage />
      <Footer />
    </>
  );
}

export default App;

```

## Link
`<a>` 標籤建議用 [[react-router-dom]]	的 `Link` 元件代替
```jsx
<Link to="/">首頁</Link>
```


#react #npm #module #routing 