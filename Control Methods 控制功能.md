---
title: "Control Methods 控制功能"
tag: 
- js/gsap
---
## Control Methods 控制功能
>[Timeline Control](https://greensock.com/get-started/#timeline-control)
```html
<!-- 這是一顆按鈕，來讓他帶有 control methods 功能 -->
<button id="pause">pasue()</button>
```
```js
document.querySelector('#pause').onclick = () => tween.pause();
```

---

- pause()
- seek(數字)
- progress(數字)
- 等

#js/gsap 