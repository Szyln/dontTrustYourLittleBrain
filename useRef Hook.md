# useRef Hook
>本篇使用 Library：[vanill-tilt](https://micku7zu.github.io/vanilla-tilt.js/index.html)
>可使用 querySelector 來讓 DOM node 有酷炫的漸層動態效果

>另參考[【Day.15】React入門 - 非控制組件與useRef](https://ithelp.ithome.com.tw/articles/10246939)

> `useRef` 的 ref 與[[物件傳參考]]中提到的 reference 是同一件事
> 指的是「變數指向記憶體位置上對應到的值」

在 React 中用原始的 DOM 方式（ `querySelector` 之類）操作元素並不直覺，使用 `useRef` [[Hook]]，可以直接在元件裡，直接操作元件

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

  // 注意：React 的 JSX 寫的終究是一個 React element 而已，
  // 不是 DOM 元素 
  return (
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
