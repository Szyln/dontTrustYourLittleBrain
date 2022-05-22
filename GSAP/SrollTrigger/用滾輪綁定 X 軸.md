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