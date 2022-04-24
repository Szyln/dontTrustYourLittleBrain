---
title: "Staggers"
tag: 
- js/gsap
---
## Staggers
設定 offset，可以讓動畫觸發產生時間差
```html
<div class='circle' />
<div class='circle' />
<div class='circle' />
<div class='circle' />
```
```js
gsap.from('.circle', {
	duration: 1, 
	opacity: 0,
	y: 150,
	stagger: 0.25		// 每個 circle 都會延遲 0.25 觸發
}) 
```

#js/gsap 