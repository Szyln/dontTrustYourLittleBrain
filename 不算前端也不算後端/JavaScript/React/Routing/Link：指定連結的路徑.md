## Link
- 取代 `<a>` ，`App()` 中的 `Routes` 元件就是透過這裡做回應
- 因為 `<a>` 會重新讀取整個頁面，[SPA](SPA.md) 的網站並不適合這樣
- `to` 所設定的路徑必須在 [Routes & Route：更改 Route 時更新頁面區塊](Routes%20&%20Route：更改%20Route%20時更新頁面區塊.md) 中設定好會更新什麼，否則不會有效果
```jsx
// 匯入 React
import { Link } from "react-router-dom";

const Nav = () => {
  return (
    <nav >
      <ul>
        <li>
          {/* 因為有設定 Route，所以這個點下去後 Routes 區塊的內容就會隨著 Link 影響 */}
          <Link to="/">首頁</Link>
        </li>
        <li>
          <Link to="/about">關於我們</Link>
        </li>
      </ul>
    </nav>
  );
};
```