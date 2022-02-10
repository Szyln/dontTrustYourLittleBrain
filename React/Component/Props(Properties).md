# Props(Properties)
每個 React Component 都有自己的 props

```jsx
// 將物件內容轉換成網頁顯示
const friend = ({name, age, desc}) => {
  return <div>
    <h1>Name: {name}</h1>
    <h2>Age: {age}</h2>
    <p>{desc}</p>
  </div>
};
```