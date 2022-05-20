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

- [滾輪參數綁定物件的 Y 軸，Y 軸數值固定：pin](滾輪參數綁定物件的%20Y%20軸，Y%20軸數值固定：pin.md)

