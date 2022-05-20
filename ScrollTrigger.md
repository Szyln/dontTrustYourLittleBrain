---
title: "ScrollTrigger"
tag: 
- js/gsap/scrolltrigger
---

##  ScrollTrigger
>[官方說明](https://greensock.com/docs/v3/Plugins/ScrollTrigger)
>[react-gsap](https://bitworking.github.io/react-gsap/src-components-scroll-trigger#basic-usage)：還沒看
```js
// 基本的樣子
// 使用外掛 ScrollTrigger
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

---

- [SrollTrigger 的預設值：trigger](SrollTrigger%20的預設值：trigger.md)
- [觸發、停止的參考物件 trigger, endTrigger](觸發、停止的參考物件%20trigger,%20endTrigger.md)
- [Toggle actions：觸發的動畫週期](Toggle%20actions：觸發的動畫週期.md)
- [參考物件的細部觸發、停止條件：start, end](參考物件的細部觸發、停止條件：start,%20end.md)
- [ScrollTrigger 的參考線：markers](ScrollTrigger%20的參考線：markers.md)
- [滾輪參數綁定動畫時間軸：scrub](滾輪參數綁定動畫時間軸：scrub.md)


- [ScrollTrigger 搭配 timeline：滾輪參數綁定總體時間軸](ScrollTrigger%20搭配%20timeline：滾輪參數綁定總體時間軸.md)

- [滾輪參數綁定物件的 Y 軸，Y 軸數值固定、滾輪停止影響物件的 Y 軸：pin](滾輪參數綁定物件的%20Y%20軸，Y%20軸數值固定、滾輪停止影響物件的%20Y%20軸：pin.md)

## ScrollTrigger 的另一種使用方法：create 
> 客製化會講更多（？

除了放在 tween 裡面，也可以把 timeline 放在 ScrollTrigger 裡
```js
gsap.registerPlugin(ScrollTrigger);
gsap.defaults({ease:'none', duration: 2});

const tl = gsap.timeline();
tl.from('.a-fullpage', {xPercent: -100})
	.from('.b-fullpage', {xPercent: 100})
	.from('.c-fullpage', {yPercent: -100});

ScrollTrigger.create({
	animation: tl,
	trigger: '#container',
	start: 'top top',
	end: '+=4000',
	scrub: true,
	pin: true,
	anticipatePin: 1
})
```

## 產生類似多個 position-sticky 區塊的效果：取消 pinSpacing
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

## 用滾輪綁定 X 軸
>好難，不太懂

先取消 X 捲軸
```css
body {
	// 取消頁面的 X 軸捲軸
	overflow-x: hidden;
}
```

```js
gsap.registerPlugin(ScrollTrigger);

let sections = gsap.utils.toArray('.panel')

gsap.to(sections, {
	xPercentL -100 * (sections.length - 1),
	ease: 'none',
	scrollTrigger: {
		trigger: '.container',
		pin: true,
		scrub: 1,
		// 沒有移到精準的區塊上的話，會自動移到最接近的區塊
		snap: 1 / (sections.length - 1),
		end: () => "+=" +
		doucment.querySelector('.container').offstWidth
	}
})
```


## 把 ScrollTrigger 當作 callback 用
除了用來作動畫，還可以把 ScrollTrigger 當成程式碼的參數來用，像是拿來 toggleClass, log, 等等
```js
gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
	toggleActions: 'restart pause resume none',
	markers: true
	
})

ScrollTrigger.create({
	trigger: '.c',
	start: 'top center',
	end: 'top 100px',
	// 可以這樣用
	onEnter: () => console.log('enter!'),
	onLeave: () => console.log('leave'),
	onEnterBack: () => console.log('enter back'),
	onLeaveBack: () => console.log('all the way back'),
	// 這個的功用不是很懂
	// self.progress 是一個 0~1 的數值，用 toFixed 限制顯示小數點下幾位
	onUpdate: (self) => console.log('update', self.progress.toFixed(3))
	// 會切換 boolean
	onToggle: (self) => console.log('toggled', self.isActive)
	// 可以拿來設定切換要不要加入指定的 class 
	toggleClass: 'active',
	// marker 用的 id
	id: 'my-id'
})

// 可以拿來做為選擇器
let trigger = ScrollTrigger.getById('my-id')
```


```js
// 取代 viewport
scroller: '#container'
```

```js
// SrollTrigger 預設是看垂直捲軸，也可以改成橫向捲軸
horizontal: true,
```