## React 中使用 timeline
>- [Sequencing with Timelines 讓動畫按照順序播](Sequencing%20with%20Timelines%20讓動畫按照順序播.md)
>- [useRef Hook](useRef%20Hook.md)

- Ref 是存在於 render 之外的，所以他可以儲存任何希望在元件的生命週期中都維持一致的內容
- 避免 timeline 在每次 render 都再建立一個，要記得在 [useEffect Hook](useEffect%20Hook.md) 內使用且使用 [useRef Hook](useRef%20Hook.md)

```jsx
function App() {
  const el = useRef();
  const q = gsap.utils.selector(el);
	// timeline 也可以用 useRef
  const tl = useRef();
      
  useEffect(() => {
    
    tl.current = gsap.timeline()
      .to(q(".box"), {
        rotate: 360
      })
      .to(q(".circle"), {
        x: 100
      });

  }, []);
  
  return (
    <div className="app" ref={el}>
      <Box>Box</Box>
      <Circle>Circle</Circle>
    </div>
  );
}
```

## 搭配 Timeline 的控制功能
>- [Sequencing with Timelines 讓動畫按照順序播](Sequencing%20with%20Timelines%20讓動畫按照順序播.md)
>	- [Timeline 的功能](Timeline%20的功能.md)

這個範例也搭配了 [useState Hook](useState%20Hook.md), [useEffect Hook](useEffect%20Hook.md) 來寫更複雜的操作
```jsx
function App() {
  const [reversed, setReversed] = useState(false);
  const el = useRef();
  const q = gsap.utils.selector(el);
  
  const tl = useRef();
      
  useEffect(() => {
    // add a box and circle animation to our timeline and play on first render
    tl.current = gsap.timeline()
      .to(q(".box"), {
        rotate: 360
      })
      .to(q(".circle"), {
        x: 100
      });
  }, []);
  
  useEffect(() => {
    // toggle the direction of our timeline
    tl.current.reversed(reversed);    
  }, [reversed]);
   
  return (
    <div className="app" ref={el}>
      <div>
        <button onClick={() => setReversed(!reversed)}>Toggle</button>
      </div>
      <Box>box</Box>
      <Circle>circle</Circle>
    </div>
  );
}
```