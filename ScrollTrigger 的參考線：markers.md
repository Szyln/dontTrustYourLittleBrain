---
title: "ScrollTrigger 的參考線：markers"
tag: 
- js/gsap/scrolltrigger
---

##  ScrollTrigger 的參考線：markers
![](Pasted%20image%2020220519163329.png)
類似動畫版的參考線，標記目前設定的動畫什麼時候觸發、結束等
```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	scrollTrigger: {
		trigger: '.c',
		start: 'top center',
		// 設定 true 啟用
		markers: true
		toggleActions: 'play pause reverse pause',
	}
	x: 400,
	rotation: 360,
	duration: 3
})
```
