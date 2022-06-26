### 注意 render 時機
>本範例的 `rotation` 的值拿掉 `+=` 的話，`dev` 模式也可以正常顯示 why
```tsx
function App() {
  // store a reference to the box div
  const boxRef = useRef();

  // wait until DOM has been rendered
  useEffect(() => {
    gsap.to(boxRef.current, { rotation: "+=360" });
  });
  
  // DOM to render
  return <div className="box" ref={boxRef}>Hello</div>;
}
```
