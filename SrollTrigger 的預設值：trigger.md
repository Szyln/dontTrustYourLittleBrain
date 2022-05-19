---
title: "SrollTrigger 的預設值：trigger"
tag: 
- js/gsap/scrolltrigger
---

##  SrollTrigger 的預設值：trigger
最基本的設定，沒有其他設定的話`scrollTrigger` 指的就是 `scrollTrigger.trigger`（其他的內容往下看）

![](觸發、停止的參考物件%20trigger,%20endTrigger#^29a084)
```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	// 滾輪滾到 .c 的時候觸發
	scrollTrigger: '.c',
	// .c 的動畫效果
	x: 400,
	rotation: 360,
	duration: 3
})
```