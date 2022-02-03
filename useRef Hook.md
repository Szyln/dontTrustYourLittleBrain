# useRef Hook
>本篇篇使用 Library
>[vanill-tilt](https://micku7zu.github.io/vanilla-tilt.js/index.html)：可使用 querySelector 來讓 DOM node 有酷炫的漸層動態效果

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
