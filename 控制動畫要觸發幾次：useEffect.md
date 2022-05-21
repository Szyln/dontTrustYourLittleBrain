## 控制動畫要觸發幾次：useEffect
使用 useEffect 的 [Dependency array](Dependency%20array.md) 來控制
```jsx
// only runs after first render
useEffect(() => {
  gsap.to(q(".box-1"), { rotation: "+=360" });
}, []);

// runs after first render and every time `someProp` changes
useEffect(() => {
  gsap.to(q(".box-2"), { rotation: "+=360" });
}, [someProp]);

// runs after every render
useEffect(() => {
  gsap.to(q(".box-3"), { rotation: "+=360" });
});
```