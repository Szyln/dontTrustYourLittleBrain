## 把 ScrollTrigger 當作 callback 用
除了用來作動畫，還可以把 `ScrollTrigger` 當成程式碼的參數來用，像是拿來 `toggleClass`, `log`, 等等
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