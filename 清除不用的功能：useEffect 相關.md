---
title: "清除不用的功能：useEffect 相關"
tag: 
- js/gsap/react
---

##  清除不用的功能：useEffect 相關
```tsx
useEffect(() => {
  const animation1 = gsap.to(".box1", { rotation: "+=360" });
  
  const animation2 = gsap.to(".box2", {
    scrollTrigger: {
      ...
    }
  });

  const onMove = () => {
    ...
  };
  window.addEventListener("pointermove", onMove);
    
  // cleanup function will be called when component is removed
  return () => {
    animation1.kill();
    animation2.scrollTrigger.kill();
    window.removeEventListener("pointermove", onMove);
  };
}, []);
```