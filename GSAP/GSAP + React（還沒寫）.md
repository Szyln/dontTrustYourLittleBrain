---
title: "GSAP + React（還沒寫）"
tag: 
- js/gsap
- js/react
---
## GSAP + React（還沒寫）
>https://greensock.com/react

### 建置
- [安裝 React](JavaScript/React/環境/安裝%20React.md)
- [GSAP 安裝](GSAP%20安裝.md)

#### 我遇到的問題
`dev`模式下  GSAP 的動畫很不精準，到 `build` 發布模式會解決，why

### 指定動畫物件：useRef
### 單個的時候
>[useRef Hook](useRef%20Hook.md)

```tsx
const boxRef = useRef();
return <div className="box" ref={boxRef}>Hello</div>;
```

### 指定複數個動畫物件：gsap.utils.selector
如果每個動畫都要設定 `ref` 太冗了，使用 GSAP 的 `gsap.utils.selector` 解決
- 類似 `.querySelectorAll()`，直接選取複數動畫物件的父層
- `gsap.utils.selector(父層).('.複數動畫物件的class名稱')` return 的值會是一個 Array

>[gsap.utils.selector](https://greensock.com/docs/v3/GSAP/UtilityMethods/selector())

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

### timeline
>- [Sequencing with Timelines 讓動畫按照順序播](Sequencing%20with%20Timelines%20讓動畫按照順序播.md)
>- [useRef Hook](useRef%20Hook.md)



#js/gsap #js/react 