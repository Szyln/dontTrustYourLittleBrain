---
title: "觸發、停止的參考物件 trigger, endTrigger"
tag: 
- js/gsap/scrolltrigger
---

##  觸發、停止的參考物件 trigger, endTrigger
```jsx
gsap.to('.c', { 
	scrollTrigger: {
			trigger: '.c',
			endtrigger: '+=300'
	},
	x: 400, 
	rotation: 360, 
	duration: 3
}
```
- `trigger`：指定滾輪滾到什麼的時候觸發動畫（不一定是動畫物件本身） ^29a084
- `endTrigger`：指定滾輪滾到什麼的時候停止動畫（不一定是動畫物件本身