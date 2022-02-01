# Dependency array
>[[useEffect Hook]] 

>[[eslint-plugin-react-hooks]] 來幫助自己寫 [[Hook]] 的時候不會東漏一個設定西漏一個設定

`useEffect` 的第二個可用參數，可以讓 [[side-effect]] 的另一端資料與 React 維持雙向同步，如果沒有另一端資料不需要被更新，就不需重新執行

```jsx
// 以下 Greeting() 的 useEffect
React. useEffect (() => {
  console.log('useEffect 被執行囉');
  window.localStorage.setItem('name', name)
  // Dependency array
	// 確認 localStorage 沒有被更新的話，就不需要隨著 App() 重新執行
}, [name])
```
```jsx
// Greeting 元件會匯入到 App 內執行
function Greeting() {
  // useState: [name, setName]
  // setName 功能
  // useEffect：建議搭配 [[Dependency array]] 來維持雙向同步
  return <欲渲染內容 />
}

function App() {
  // 每次 count 更新，就會 re-render App()
  const [count, setCount] = React.useState(0)

  // 每次 App() render，Greeting() 元件就會被 render
	// render 時，Greeting() 的 useEffect 會一起被執行
  return (
    <>
      <button onClick={() => setCount(c => c + 1)}>{count}</button>
      <Greeting />
    </>
  )
}
```
