---
title: "gsap.to"
tag: 
- js/gsap
---
## gsap.to
從原始狀態變化到指定狀態
```js
gsap.to('.logo', {		// 要讓他動畫的目標，可多個（用 , 隔開）（selector, 變數, 物件, 陣列都可以）
	duration: 2,
	x: 300, 
	backgroundColor: '#560563',
	borderRadius: '20%',					// 要變成 string 不然會被判定成餘數
	border: '5px solid white',
	ease: 'back'

})
```

#js/gsap 