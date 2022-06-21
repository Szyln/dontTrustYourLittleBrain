---
title: "React 中動態更改 HTML Title 標籤"
tag: 
- js/react/route
---

##  React 中動態更改 HTML Title 標籤
>- [react-document-title](https://github.com/gaearon/react-document-title)
>- 搭配 [React Router(react-router-dom)](React%20Router(react-router-dom).md) 使用
>- 如果要變更其他 html meta：[react-document-meta](https://github.com/kodyl/react-document-meta)

```shell
npm install --save react-document-title
```
匯入
```jsx
// 匯入，記得不要寫成 import { DoucmentTitle }
import DocumentTitle from 'react-document-title';
```
在設定 router 的地方外面加入預設 title
```jsx
function App() {
  // Use "My Web App" if no child overrides this
  return (
    <DocumentTitle title='預設 title'>
      {/* 多個 router 寫在這裡 */}
    </DocumentTitle>
  );
}
```

再到各個頁面設定標題，包在每個頁面之外
```jsx
function HomePage() {
  // Use "Home" while this component is mounted
  return (
    <DocumentTitle title='首頁'>
      {/* 首頁的內容 */}
    </DocumentTitle>
  );
}
```