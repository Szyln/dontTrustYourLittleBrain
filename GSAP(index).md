---
title: "GSAP(index)"
tag: 
- js/gsap 
- animation
- css
- index
---
## GSAP
- [GSAP 安裝](GSAP%20安裝.md)

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

- [[gsap.to]]: 從原始狀態變化到指定狀態
- [[gsap.from]]: 從指定狀態變化到原始狀態 
- `gsap.fromTo`


## 設定
- [[Staggers]]：設定每個動畫的時間差
- [[設定起始點隨機]]
### 目錄
- [可以使用 GSAP 的資料類型](可以使用%20GSAP%20的資料類型.md)
- [GSAP 觸發事件](GSAP%20觸發事件.md)
- [[Control Methods 控制功能]]：控制時間軸的功能


#js/gsap #animation #css