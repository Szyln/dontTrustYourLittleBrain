---
title: "GSAP + React"
tag: 
- js/gsap
- js/react
---

##  GSAP + React
>https://greensock.com/react

- [GSAP + React 建置](GSAP%20+%20React%20建置.md)
- [指定動畫物件：useRef](指定動畫物件：useRef.md)
- [注意 render 時機](注意%20render%20時機.md)
- [React 中使用 timeline](React%20中使用%20timeline.md)
- [依照元件的 state 狀態要怎麼觸發動畫：useEffect](依照元件的%20state%20狀態要怎麼觸發動畫：useEffect.md)
- [互動式動畫](互動式動畫.md)

## 網站讀取時，避開非預期的物件閃現 FOUC
>- [Avoiding flash of unstyled content (FOUC)](https://greensock.com/react#avoidingFlashOfUnstyledContentFOUC)
>- [useEffect vs useLayoutEffect](https://kentcdodds.com/blog/useeffect-vs-uselayouteffect).

- `useEffect` 會在 DOM 生成後執行
- 可以用 `useLayoutEffect` 取代，唯一的差別就是他是在 DOM 生成前執行

![longerfouc.gif](https://greensock.com/uploads/monthly_2021_08/longerfouc.gif.29308cf3ff539b4ec3ed291e726cb210.gif)

### 會用到的時刻
- DOM measurements
- [ScrollTrigger](ScrollTrigger.md) plugin
- [FLIP](https://greensock.com/docs/v3/Plugins/Flip) plugin


### 範例
>- [codepen](https://codepen.io/GreenSock/pen/XWRBbYZ)
```jsx
// simulate loading data from a server
function fetchFakeData() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve([
        { id: 1, color: "blue" },
        { id: 2, color: "red" },
        { id: 3, color: "purple" },
      ]);
    }, 2000);
  });  
}
```
```jsx
function App() {
  const el = useRef();
  const q = gsap.utils.selector(el);
  
  const [data, setData] = useState([]);
	// loading 代表正在從資料庫（透過 api）取得資料
  const [loadingState, setLoadingState] = useState();
  
  useEffect(() => {
    
    if (loadingState !== "start") return;
    
    const loadData = async () => {
      const data = await fetchFakeData();
      setData(data);
      setLoadingState("complete");
    }
    loadData();    
    
  }, [loadingState]);
  // 動畫用 useLayoutEffect 執行
  useLayoutEffect(() => {
    
    if (loadingState !== "complete") return;
    
    gsap.fromTo(q(".box"), {
      opacity: 0
    }, {
      opacity: 1,
      duration: 1,
      stagger: 0.2
    });
  }, [loadingState]);

  const startLoading = () => {
    if (!loadingState) {
      setLoadingState("start");
    }
  };
  
  return (
    <div className="panel flex-row" ref={el}>
      {
        !loadingState
          ? <div><button onClick={startLoading}>Start Loading</button></div>
          : null
      }          
      { 
        loadingState === "start" 
          ? <div className="loading">Loading fake data...</div> 
          : null 
      }
      {
        data.map(item => <Box key={item.id} {...item }>Box {item.id}</Box>)
      }
    </div>
  );
}
```