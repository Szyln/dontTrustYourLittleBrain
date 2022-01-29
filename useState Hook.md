# useState Hook
>[[Event Handlers]]
>[[State]]
>[[Hook]]

```jsx
function 
function handleChange(event) {
  setState({username: event.target.value})
}

function setState(newState) {
	Object.assign(state, newState)
	renderApp()
}
```
```jsx
function Greeting() {
	// destructing assignment
  const [name, setName] = React.useState('')
  const handleChange = event => setName(event.target.value)
  return (
    <div>
      <form>
        <label htmlFor="name">Name: </label>
        <input onChange={handleChange} id="name" />
      </form>
      {name ? <strong>Hello {name}</strong> : 'Please type your name'}
    </div>
  )
}

ReactDOM.render(<Greeting />, document.querySelector('#root'))
```
>[[Destructing Assignment]]]

```jsx
// React.useState('') 記錄的是一個 array 儲存狀態
// () 內的參數是原始狀態
// [] 內第一個變數對應顯示在網頁上的位置，第二個是對應
const [name, setName] = React.useState('')
```

#react #js #hook