# useEffect Hook
處理 [[side-effect]] 的 hook

## 以儲存資料到 [[Local Storage]] 為例
```jsx
const [name, setName] = React.useState('')

  React.useEffect(() => {
    window.localStorage.setItem('name', name)
  })
```
```jsx
function Greeting() {
  const [name, setName] = React.useState(
    window.localStorage.getItem('name') || '',
  )

  React.useEffect(() => {
    window.localStorage.setItem('name', name)
  })

  const handleChange = event => setName(event.target.value)

  return (
    <div>
      <form>
        <label htmlFor="name">Name: </label>
        <input value={name} onChange={handleChange} id="name" />
      </form>
      {name ? <strong>Hello {name}</strong> : 'Please type your name'}
    </div>
  )
}
```
