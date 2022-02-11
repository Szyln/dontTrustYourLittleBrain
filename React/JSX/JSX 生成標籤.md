# JSX 生成標籤

[[生成標籤：React.createElement()]]寫起來並沒有效率，透過 [[JSX]] 格式來寫可以更接近 HTML 

```jsx
// JSX 寫法
const HellowElement = <h1 className="title">Hello World</h1>
```
```jsx
// JSX 編譯後：[[React 基本原理]]
const HelloElement = React.createElement(
  'h1',
  { className: 'title' },
  'Hello World'
)
```

## HTML 透過存到變數內來重複使用
JSX 可以讓 html 像 js 一樣重複利用

>事前知識：[[JSX 內的 HTML 加入 JS 程式碼]]
>如果是要元件重複利用（可以導入參數）：[[Component：可重複利用、自定參數的元件]]

```jsx
const HellowElement = <h1 className="title">Hello World</h1>
const element = (
  <div>
    {HelloElement}
  </div>
)
```
#react #html #js