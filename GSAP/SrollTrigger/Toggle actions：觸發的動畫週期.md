---
title: "Toggle actions：觸發的動畫週期"
tag: 
- js/gsap/scrolltrigger
---

##  Toggle actions：觸發的動畫週期
`scrollTrigger`不只可以指定什麼時候觸發，還可以更詳細的指定動畫週期
- 觸發動作
- 觸發完動作
- 回歸時的動作
- 目標離開畫面後的動作
```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	scrollTrigger: {
		// 滾輪滾到 .c 的時候觸發
		trigger: '.c',
		// 四個動作皆可以填入上面任一動作
		// '觸發動作 觸發完動作 回歸時的動作 目標離開畫面後動作'
		toggleActions: 'play pause reverse pause'
	}
	// .c 的動畫效果
	x: 400,
	rotation: 360,
	duration: 3
})
```

#### 可以指定的 toggle actions
- play：一次性觸發
- pause：離開觸發點後暫停
- resume：解除暫停狀態
- reverse：倒帶
- restart：不論幾次都會重啟
- reset
- complete
- none