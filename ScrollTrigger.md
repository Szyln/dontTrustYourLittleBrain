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
- resume
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
		// '觸發動作 離開動作 回歸觸發動作 offscreen時的動作'
		toggleActions: 'play pause reverse pause'
	}
	// .c 的動畫效果
	x: 400,
	rotation: 360,
	duration: 3
})
```

