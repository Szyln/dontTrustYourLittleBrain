---
title: "滾輪參數綁定動畫時間軸：scrub"
tag: 
- js/gsap/scrolltrigger
---

##  滾輪參數綁定動畫時間軸：scrub
- `true`：時間軸無加速度（ease, 延遲）的對準滾輪參數
- `number`：時間軸有加速度（ease, 延遲）的對準滾輪參數，數字對應秒數

```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	scrollTrigger: {
		trigger: '.c',
		start: 'top center',
		markers: true,
		// true 啟用，也可以輸入數值
		scrub: true,
		toggleActions: 'play pause reverse pause',
	}
	x: 400,
	rotation: 360,
	duration: 3
})
```