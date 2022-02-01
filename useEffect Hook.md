# useEffect Hook
處理 [[side-effect]] 的 [[Hook]]

## 以儲存資料到 [[Local Storage]] 為例
```jsx
const [name, setName] = React.useState('')

// name 有內容時，就更新 localStorage（注意：這是單向更新）
React.useEffect(() => {
  console.log('Greeting useEffect 被執行囉');
  window.localStorage.setItem('name', name)
  // Dependency array：讓 useEffect 變成雙向更新，如果沒有更新就不執行這個 hook
}, [name])
```
```jsx
function Greeting() {
  // [[useState Hook]]
  const [name, setName] = React.useState(
    // [[Logic OR]]
    // 取得 localStorage 是否有這個值，否則預設值為空字串
    window.localStorage.getItem('name') || '',
  )
  // useEffect：每次 greeting 執行，就 name 存進 localStorage
  React.useEffect(() => {
    window.localStorage.setItem('name', name)
  })

  const handleChange = event => setName(event.target.value)

  return (
    <div>
      <form>
        <label htmlFor="name">Name: </label>
        {/* 
          將 value 設定為 {name} 這樣每次重整（從 localStorage 抓到資料時）
          這裡也會顯示 
        */}
        <input value={name} onChange={handleChange} id="name" />
      </form>
      {name ? <strong>Hello {name}</strong> : 'Please type your name'}
    </div>
  )
}
```
> [[Logic OR]]