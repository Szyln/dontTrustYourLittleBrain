---
title: "參考物件的細部觸發、停止條件：start, end"
tag: 
- js/gsap/scrolltrigger
---

##  參考物件的細部觸發、停止條件：start, end

調整觸發、結束時機點，原本是預設一滾到指定物件就開始
```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	scrollTrigger: {
		trigger: '.c',
		// 改為物件被滾到 window 正中央開始
		// 第一個 top： 相對指定動畫物件的位置
		// 第二個 center：相對指定容器的相對位置
		start: 'top center',
		// [[ScrollTrigger markers]]
		markers: true
		toggleActions: 'play pause reverse pause',
	}
	// .c 的動畫效果
	x: 400,
	rotation: 360,
	duration: 3
})
```

```js
// 20px: 相對指定動畫物件的位置 .c 物件的 由 top 往下數 20px
// 80% 相對指定容器的相對位置 viewport 由 top 往下數 80%
start: '20px 80%'
```
- top
- center
- bottom
- pixels(relative to top)
- %(relative to top)
- function

#### end
另外還可用相對單位
```js
// px 可以省略
// 在 start 後 300 後結束
end: '+=300px'
```