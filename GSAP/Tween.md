## Tween
>[Tween](https://greensock.com/docs/v3/GSAP/Tween)

每一個這個動作都稱為一個 tween

```js
gsap.to({填入作用目標}, { // 可以是選擇器、物件、陣列、變數，可以多個（, 隔開）
	duration: 2,
	x: 300, 
	backgroundColor: '#560563',
	borderRadius: '20%',					// 要變成 string 不然會被判定成餘數
	border: '5px solid white',
	ease: 'back'
})
```

>ease 的工具：[ease-visualizer](https://greensock.com/ease-visualizer)

---

- [[GSAP/gsap.to]]: 從原始狀態變化到指定狀態
- [[GSAP/gsap.from]]: 從指定狀態變化到原始狀態 
- `gsap.fromTo`