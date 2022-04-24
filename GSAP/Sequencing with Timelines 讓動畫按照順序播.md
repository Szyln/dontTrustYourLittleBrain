---
title: "Sequencing with Timelines 讓動畫按照順序播"
tag: 
- js/gsap
---
## Sequencing with Timelines 讓動畫按照順序播
### 原本狀況
- 原始設定時，動畫都是同時播放，可以用 delay 來延遲
- 但這並不實際，動畫變複雜之後會算不完
```js
// 1.5 秒播完
gsap.from('.a', { duration: 1.5 })
// 延遲到 1.5 秒後開始播
gsap.from('.b', { duration: 1, delay: 1.5 })

```

## timeline()
`timeline()` 可以讓動畫都設定成一個結束後播下一個
```js
// 加入 timeline 功能
const tl = gsap.timeline()

tl.from('.a', { duration: 1.5 })
// 這樣就可以拿掉 delay 了
tl.from('.b', { duration: 1 })
```

- [[GSAP/動畫間加入時間間格]]
- [[GSAP/為時間間格加入標籤]]
- [[GSAP/重複播放 timeline]]
- [[GSAP/倒帶 timeline]]

#js/gsap/timeline 