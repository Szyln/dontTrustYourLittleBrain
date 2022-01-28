# Event Handlers
 [可以上文件查有支援什麼 Event](https://reactjs.org/docs/events.html#supported-events) 
 
 ```jsx
const state = {eventCount: 0, username: ''}

function App() {
  function handleClick() {
    setState({eventCount: state.eventCount + 1})
  }

  function handleChange(event) {
    setState({username: event.target.value})
  }

  return (
    <div>
      <p>There have been {state.eventCount} events.</p>
      <p>
        <button onClick={handleClick}>Click Me</button>
      </p>
      <p>You typed: {state.username}</p>
      <p>
        <input onChange={handleChange} />
      </p>
    </div>
  )
}

function setState(newState) {
	// 在 state 物件中展開（淺層拷貝） newState 物件
  Object.assign(state, newState)
  renderApp()
}

function renderApp() {
  ReactDOM.render(<App />, document.querySelector('#root'))
 ```
 
 >[[物件不要傳參考的時候：深層、淺層拷貝#淺層拷貝 Shallow Copy]]