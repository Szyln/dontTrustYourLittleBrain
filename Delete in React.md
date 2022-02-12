# Delete in React
>用 [[State Lifting]] 的範例

目前內容
- `<App />` ：母層，[[State Lifting]] 有 input, message 的 state
	- `<Create />`：子層，輸入 input 用（存到 message）
	- `<Info />`：子層，顯示 message
		- `<Message />` ：孫層，每個 message 條目

```jsx
// 匯入 UUID 來生成 key prop
import { v4 as uuidv4 } from 'uuid';

// 有 state lifting 到母層
const Create = ({message, setMessage}) => {
  const submitHandler = (e) => {
    e.preventDefault()
		// 剛生成 message 的時候就可以給她 key prop 了
    setMessage([...message, {input, id: uuidv4()}])
    setInput("")
  }
  const inputHandler = (e) => {
    setInput(e.target.value)
  }
  return (
    <form>
      <input type="text" onChange={inputHandler} value={input} />
      <input type="button" onClick={submitHandler} value="Submit" />
    </form>
  )
}
```
>[[Key prop]]
```jsx
const Info = ({message, setMessage}) => {
	return (
		<ul>
			{message.map (msg => (
				<Message key={msg} msg={msg.input} message={message} setMessage={setMessage} key={msg.id} />)}
			)
		</ul>	
	)
}
```

```jsx
// 孫層
const Message = ({msg, message, setMessage}) => {
	const deleteHandler = () => {
		setMessage(message.filter(m => m.id !== msg.id))
	}
	return (
		<li>
			<p>{msg.input}</p>
			<button onClick={deleteHandler}>刪除</button>
		</li>
	)
}
```
>[[filter()]]  




#react 