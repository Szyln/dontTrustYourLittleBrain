---
title: "對目標設定多個動畫：GSAP keyframes"
tag: 
- js/gsap
---

##  對目標設定多個動畫：GSAP keyframes

```js
gsap.to('.box', {
  keyframes: [
    { duration: 1, x: 100, },
    { duration: 1, y: 100 },
    { duration: 1, rotation: 360 },
  ]
});
```

#js/gsap