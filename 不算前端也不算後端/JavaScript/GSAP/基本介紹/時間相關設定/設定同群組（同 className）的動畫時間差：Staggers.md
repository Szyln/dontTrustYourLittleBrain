---
title: "設定同群組（同 className）的動畫時間差：Staggers"
tag: 
- js/gsap
---

##  設定同群組（同 className）的動畫時間差：Staggers
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

>- 不同群組的會用 delay 或更複雜的用 timeline 設定
>- [Sequencing with Timelines 讓動畫按照順序播](Sequencing%20with%20Timelines%20讓動畫按照順序播.md)
>- 無法搭配 [ScrollTrigger](ScrollTrigger.md) 使用
