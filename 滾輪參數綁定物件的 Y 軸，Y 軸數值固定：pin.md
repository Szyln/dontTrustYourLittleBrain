---
title: "滾輪參數綁定物件的 Y 軸，Y 軸數值固定：pin"
tag: 
- 
---

##  滾輪參數綁定物件的 Y 軸，Y 軸數值固定：pin
- `true`:  pin 物件動畫本身
- `其他 DOM node`: 不影響物件本身，綁定在其他 node 的 Y 軸上


### pin 物件動畫本身
```js
gsap.registerPlugin(ScrollTrigger);

gsap.to('.c', {
	scrollTrigger: {
		trigger: '.c',
		start: 'top center',
		markers: true,
		scrub: true,
		// pin 為真時，這個 tween 的動畫物件 Y 軸會隨著滾輪增加
		pin: true
	}
	// 同時這裡的動畫設定也會運行
	x: 400,
	rotation: 360,
	duration: 3
})
```

### pin 其他物件
```js
// 該 tween 動畫物件不會影響，但 pin 的這個 .b 在 tween 的運作期間隨著滾輪增加 Y 軸
pin: '.b'
```

#js/gsap/scrolltrigger 