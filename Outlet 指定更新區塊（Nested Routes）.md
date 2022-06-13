---
title: "Outlet 指定更新區塊（Nested Routes）"
tag: 
- js/react 
- js/module/npm 
- routing
---

##  Outlet 指定更新區塊（Nested Routes）
> 接續[再一層的 Route 指定渲染元件（Nested Routes）](再一層的%20Route%20指定渲染元件（Nested%20Routes）.md)

`Outlet` 存在於上層 Route 渲染出來的元件內

```jsx
import { Outlet, Link } from "react-router-dom";

export default function Cart() {
  return (
    <div>
      <h1>購物車</h1>
      <nav>
				{/* 實際這兩個 Link 是指向：cart/invoices, cart/expenses */}
        <Link to="/invoices">發票</Link> 
        <Link to="/expenses">費用</Link>
      </nav>
			{/* 上面兩個 Route 的渲染結果會在 Outlet 中呈現 */}
      <Outlet />
    </div>
  );
}
```