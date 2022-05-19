---
title: "ScrollTrigger"
tag: 
- js/gsap/scrolltrigger
---

##  ScrollTrigger
### 按照滾輪的時機點「觸發」動畫
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

### Toggle actions
`scrollTrigger`不只可以指定什麼時候觸發，還可以更靈活的狀態設定
- play：一次性觸發
- pause：離開觸發點後暫停
- resume：解除暫停狀態
- reverse
- restart：不論幾次都會重啟
- reset
- complete
- none

```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	scrollTrigger: {
		// 滾輪滾到 .c 的時候觸發
		trigger: '.c',
		// 四個動作皆可以填入上面任一動作
		// '觸發動作 觸發完動作 回歸時的動作 offscreen時的動作'
		toggleActions: 'play pause reverse pause'
	}
	// .c 的動畫效果
	x: 400,
	rotation: 360,
	duration: 3
})
```

### start
調整觸發時機點，原本是預設一滾到指定物件就開始
- top
- center
- bottom
- pixels(relative to top)
- %(relative to top)

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

#### ScrollTrigger markers
![](Pasted%20image%2020220519163329.png)
類似動畫版的參考線，動畫什麼時候觸發、結束等