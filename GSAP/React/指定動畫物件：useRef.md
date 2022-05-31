---
title: "指定動畫物件：useRef"
tag: 
- js/gsap/react
---

##  指定動畫物件：useRef
### 單個的時候
>[useRef Hook](useRef%20Hook.md)

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

### 指定複數個動畫物件：gsap.utils.selector
如果每個動畫都要設定 `ref` 太冗了，使用 GSAP 的 `gsap.utils.selector` 解決

> [gsap.utils.selector](gsap.utils.selector.md)

```jsx
function App() {
  const el = useRef();
  const q = gsap.utils.selector(el);
  
  useEffect(() => {
    
    // q('.box')指定到 q 底下的 .box，是一個 array 
    gsap.to(q(".box"), {
      x: 100,
      stagger: 0.33,
      repeat: -1,
      repeatDelay: 1,
      yoyo: true
    });
  }, []);
  
  return (
    <div className="app" ref={el}>
			{/* Box 元件都帶有 .box */} 
      <Box>Box</Box>
			<Container><Box>Box</Box></Container>
      <Box>Box</Box>
    </div>
  );
}
```
### 指定複數個物件，當中的幾個物件
可以把複數個 `ref` 放到 array 裡面來當作 tween 的對象 
```jsx
function App() {
  const box1 = useRef();
  const box2 = useRef();
  
  useEffect(() => {
    const boxes = [
      box1.current,
      box2.current,
    ];
    
    // Target the two specific elements we have forwarded refs to
    gsap.to(boxes, {
      x: 100,
      repeat: -1,
      repeatDelay: 1,
      yoyo: true
    });
    
  }, []);
  
  return (
    <div className="app">
			{/* Box 元件都帶有 .box */} 
      <Box ref={box1}>Box</Box>
      <Container><Box>Box</Box></Container>
      <Box ref={box2}>Box</Box>
    </div>
  );
}
```