# useState Hook
```jsx
function Greeting() {
	const stateArray = React.useState('')
	const name = stateArray[0]
	const setName = stateArray[1]
  // const [name, setName] = React.useState('')
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
>[[從物件中提取屬性到變數中 Destructing an object]]