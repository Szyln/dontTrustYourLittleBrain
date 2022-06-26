### gsap.utils.random
>- [gsap.utils.random()](https://greensock.com/docs/v3/GSAP/UtilityMethods/random())
- `gsap.utils.random()` 帶入的參數分別為
	- 範圍下限
	- 範圍上限
	- snapping increment（可以被選到的數字是一次遞增多少，例如 5 的話，就是 -200, -195, -190 ..... 195, 200）
	- 變成 return 的值（可以存到一個 function 內作使用）

>[依照元件的 state 狀態要怎麼觸發動畫：useEffect](依照元件的%20state%20狀態要怎麼觸發動畫：useEffect.md)


這個範例也是搭配 useEffect 的觸發時機寫的，用 random 做按鈕，每次只要觸發按鈕，useEffect 的 [Dependency array](Dependency%20array.md) 就會更新，進而觸發動畫
```jsx
const { useEffect, useRef, useState } = React;

const randomX = gsap.utils.random(-200, 200, 1, true);

function Box({ children, endX }) {    
  const boxRef = useRef();

  // run when `endX` changes
  useEffect(() => {
    gsap.to(boxRef.current, {
      x: endX
    });
  }, [endX]);
  
  return <div className="box" ref={boxRef}>{children}</div>;
}

function App() {  
  const [endX, setEndX] = useState(0);
    
  return (
    <div className="app">
      <button onClick={() => setEndX(randomX())}>Pass in a randomized value</button>
      <Box endX={endX}>{endX}</Box>
    </div>
  );
}
```