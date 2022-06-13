---
title: "再一層的 Route 指定渲染元件（Nested Routes）"
tag: 
- js/react
- js/module/npm
- routing
---

##  再一層的 Route 指定渲染元件（Nested Routes）
`path`不寫 `/`，完整路徑為：`上層路徑/${path}`
```jsx
import { render } from "react-dom";
import {
  BrowserRouter,
  Routes,
  Route,
} from "react-router-dom";
import Home from "./home";
import Cart from "./cart";
import Expenses from "./routes/expenses";
import Invoices from "./routes/invoices";

const rootElement = document.getElementById("root");
render(
  <BrowserRouter>
    <Routes>
      <Route path="/" element={<Home />}>
      <Route path="/cart" element={<Cart />}>
        <Route path="expenses" element={<Expenses />} />
        <Route path="invoices" element={<Invoices />} />
      </Route>
    </Routes>
  </BrowserRouter>,
  rootElement
);
```