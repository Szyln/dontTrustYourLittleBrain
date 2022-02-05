# useRef Hook
>本篇使用 Library：[vanill-tilt](https://micku7zu.github.io/vanilla-tilt.js/index.html)
>可使用 querySelector 來讓 DOM node 有酷炫的漸層動態效果

>另參考[【Day.15】React入門 - 非控制組件與useRef](https://ithelp.ithome.com.tw/articles/10246939)

> `useRef` 的 ref 與[[物件傳參考]]中提到的 reference 是同一件事
> 指的是「變數指向記憶體位置上對應到的值」

- 在 React 中用原始的 DOM 方式（ `querySelector` 之類）操作元素並不直覺，使用 `useRef` [[Hook]]，可以直接在元件裡，直接操作元件
- 不會觸發 re-render
```jsx
function Tilt() {
  // 這變數存有一個 object，其中有 current 屬性可以使用，可以顯示當前 DOM node
  const tilteRef = React.useRef()
  // 這樣用 current 不會成功，因為還沒有渲染 return 裡面的內容
  console.log(tiltRef.current)
  // useEffect 使這個在 render 完後執行
  React.useEffect(() => {
    const tiltNode = tiltRef.current
    //  vanilla-tilt 的 設定
    const vanillaTiltOptions = {
      max: 25,
      speed: 400,
    }
    // vanilla-tilt 的設定: 將 vanillaTiltOptions 賦予到 tiltNode 這個 DOM node 上
    VanillaTilt.init(tiltNode, vanillaTiltOptions)
		//  
		return () => {
			tiltNode.vanillaTilt.destroy()
		}
  })
  return (
    // useRef
    <div ref={tiltRef} className="tilt-root">
    </div>
  )
}
```
>[[useEffect Hook]]
```jsx
function Tilt({children}) {
  const tiltRef = React.useRef()

  React.useEffect(() => {
    const tiltNode = tiltRef.current
    const vanillaTiltOptions = {
      max: 25,
      speed: 400,
      glare: true,
      'max-glare': 0.5,
    }
    VanillaTilt.init(tiltNode, vanillaTiltOptions)
    return () => {
      tiltNode.vanillaTilt.destroy()
    }
  }, [])

  // 注意：React 的 JSX 寫的終究是一個 React element 而已
  // （Render 出來的結果才是 DOM 元素）
  // 不是 DOM 元素 
  return (
    // 放入 ref prop 可以讓他有
    <div ref={tiltRef} className="tilt-root">
      <div className="tilt-child">{children}</div>
    </div>
  )
}

function App() {
  const [showTilt, setShowTilt] = React.useState(true)
  return (
    <div>
      <label>
        <input
          type="checkbox"
          checked={showTilt}
          onChange={e => setShowTilt(e.target.checked)}
        />{' '}
        show tilt
      </label>
      {showTilt ? (
        <Tilt>
          <div className="totally-centered">vanilla-tilt.js</div>
        </Tilt>
      ) : null}
    </div>
  )
}
```
