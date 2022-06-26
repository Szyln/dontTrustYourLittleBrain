---
title: "依照元件的 state 狀態要怎麼觸發動畫：useEffect"
tag: 
- js/gsap/hook
---

##  依照元件的 state 狀態要怎麼觸發動畫：useEffect
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

>[gsap.utils.random](gsap.utils.random.md) 
>這個範例也是搭配 useEffect 的觸發時機寫的
>用 random 做按鈕，每次只要觸發按鈕，useEffect 的 [Dependency array](Dependency%20array.md) 就會更新，進而觸發動畫