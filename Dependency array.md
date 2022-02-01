# Dependency array
>[[useEffect Hook]] 

>[[eslint-plugin-react-hooks]] 來幫助自己寫 [[Hook]] 的時候不會東漏一個設定西漏一個設定

`useEffect` 的第二個可用參數，由於 React 經常使用元件，例如 `App()` 
利用 Dependency array 設定如果 [[Local Storage]] 沒有被更動的話，就不用執行 `useEffect`

```jsx
// Greeting 元件會匯入到 App 內執行
function Greeting() {
  // useState: [name, setName]
  // setName 功能
  // useEffect
  return <欲渲染內容 />
}

function App() {
  // 每次 count 更新，就會 re-render App()
  const [count, setCount] = React.useState(0)

  // 每次 App() render，Greeting() 元件就會被 render
  return (
    <>
      <button onClick={() => setCount(c => c + 1)}>{count}</button>
      <Greeting />
    </>
  )
}
```
```jsx
React.useEffect(() => {
  console.log('useEffect 被執行囉');
  window.localStorage.setItem('name', name)
  // Dependency array：確認 localStorage 沒有被更新的話，就不需要重新執行
}, [name])
```