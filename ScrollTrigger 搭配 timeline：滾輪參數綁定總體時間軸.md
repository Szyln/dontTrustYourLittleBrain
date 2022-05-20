---
title: "ScrollTrigger 搭配 timeline：滾輪參數綁定總體時間軸"
tag: 
- js/gsap/scrolltrigger
- js/gsap/timeline 
---

##  ScrollTrigger 搭配 timeline：滾輪參數綁定總體時間軸
```js
gsap.registerPlugin(ScrollTrigger);

let tl = gsap.timeline({
	scrollTrigger: {
		trigger: '.c',
		start: 'top center',
		markers: true,
		// true 啟用，也可以輸入數值
		scrub: true,
		toggleActions: 'play pause reverse pause',
	}
})
tl.to('.c', {
	// 時間軸已經被綁定到滾輪上
	x: 400,
	rotation: 360,
	duration: 3
})
.to('.c', {
	backgroundColor: 'purple',
	duration: 1
})
// 可以不停串下去
```
