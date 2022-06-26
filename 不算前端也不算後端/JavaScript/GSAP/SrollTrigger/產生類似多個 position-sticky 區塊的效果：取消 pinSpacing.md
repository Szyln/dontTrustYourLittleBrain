## 產生類似多個 position-sticky 區塊的效果：取消 pinSpacing
- true：`pin` 會產生 padding，維持有 `pin` 的區塊跟下一區塊不會產生重疊，或影響下一塊的重疊
```js
gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.create({
	// 一塊寬100%高沒有100%的區塊
	trigger: '#一塊',
	start: 'top top'.
	// 因為 pin，一塊下面會產生 300px 的 padding，直到動畫結束
	end: '+=300px',
	// 承上，如果取消 pinSpacing 的話會產生類似連續 position-sticky 的效果，後來的區塊會疊加在原來的區塊
	pinSpacing: false,
	// #一塊啟動時 Y 軸固定，不受滾輪影響
	pin: true,
})
```