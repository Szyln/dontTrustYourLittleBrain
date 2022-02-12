# Delete in React
>用 [[State Lifting]] 的範例

目前內容
- `<App />` ：母層，[[State Lifting]] 有 input, message 的 state
	- `<Create />`：子層，輸入 input 用（存到 message）
	- `<Info />`：子層，顯示 message
		- `<Message />` ：孫層，每個 message 條目

>[[Key prop]]
## 取得 list 資料 -> 存到 array（state）
撰寫 list 的時候，React 會因為沒有加上 `key` 這個唯一性的屬性而跳出警示
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
>### 為什麼需要 key
>因為用其他非唯一性的屬性作為 event handler 的參考的話，很容易出現問題
> >[[Delete in React]]
>
> ```jsx
> // 例如做刪除 list 功能時
>const deleteHandler = () => {
>// 使用文字做基準的話，有兩個 li 都是相同內文的話就會一起刪掉
>setMessage (message. filter (m => m !== msg))
>}
> ```

```jsx
const Info = ({message, setMessage}) => {
	return (
		<ul>
			{/* 在 Create 當中被儲存的每個 message 都有 input, id 屬性（一起被 lift 了） */}
			{
        message.map(msg =>
          <Message key={msg} msg={msg.input} message={message} setMessage={setMessage} key={msg.id} />
        )
      }
		</ul>	
	)
}
```

```jsx
// 孫層
const Message = ({msg, message, setMessage}) => {
	const deleteHandler = () => {
		// 因為是刪除功能，所以點擊到要刪除的 message 每個 message 的 id
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