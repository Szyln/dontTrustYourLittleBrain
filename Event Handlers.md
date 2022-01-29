# Event Handlers
>[可以上文件查有支援什麼 Event](https://reactjs.org/docs/events.html#supported-events) 


```jsx
  // state 變數儲存要顯示到網頁上的值（event 觸發會更動）
  const state = { eventCount: 0, username: "" };
  // 正規應該不會這樣寫，之後再學
  function renderApp() {
    ReactDOM.render(<App />, document.querySelector("#root"));
  }

  function App() {
    // 設定功能要執行的動作
    // 給 onClick event 的功能，event 觸發後便更新 state.eventCount
    function handleClick() {
      state.eventCount += 1;
      renderApp();
    }
    // 給 onChange 的功能，event 觸發後便將 state
    function handleChange(event) {
      state.username = event.target.value;
      renderApp();
    }

    return (
      <div>
        <p>There have been {state.eventCount} events.</p>
        <p>
          {/* 事件觸發的函式 hadleClick 拉上去寫 */}
          <button onClick={handleClick}>Click Me</button>
        </p>
        <p>You typed: {state.username}</p>
        <p>
          <input onChange={handleChange} />
        </p>
      </div>
    );
  }
  // 要先 render 一次頁面
  renderApp();
```
>React 支援的 Event Handlers 也可以讀取到原生的 Event Handlers
>```jsx
>function someKindOfFunction(event) {
>  console.log(event.nativeEvent)
>}
>```

## 補充
課程原本是這樣寫，上述有改成自己比較直覺的理解方式
```jsx
// 課程原本寫的事件是這樣寫
function handleClick() {
  setState({eventCount: state.eventCount + 1})
}
// 給 onChange 的功能，event 觸發後便將 state 
function handleChange(event) {
  setState({username: event.target.value})
}

function setState(newState) {
Object.assign(state, newState)
renderApp()
}
```
>[[物件不要傳參考的時候：深層、淺層拷貝#淺層拷貝 Shallow Copy]]

 