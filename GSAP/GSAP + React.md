---
title: "GSAP + React"
tag: 
- js/gsap
- js/react
---

##  GSAP + React
>https://greensock.com/react

- [GSAP + React 建置](GSAP%20+%20React%20建置.md)
- [指定動畫物件：useRef](指定動畫物件：useRef.md)
- [注意 render 時機](注意%20render%20時機.md)
- [React 中使用 timeline](React%20中使用%20timeline.md)
- [依照元件的 state 狀態要怎麼觸發動畫：useEffect](依照元件的%20state%20狀態要怎麼觸發動畫：useEffect.md)
- [互動式動畫](互動式動畫.md)

## Avoiding flash of unstyled content (FOUC) 
>[Avoiding flash of unstyled content (FOUC)](https://greensock.com/react#avoidingFlashOfUnstyledContentFOUC)

As `useEffect` fires after the DOM has been painted, when fading in elements you may notice an undesired flash of unstyled content.

![longerfouc.gif](https://greensock.com/uploads/monthly_2021_08/longerfouc.gif.29308cf3ff539b4ec3ed291e726cb210.gif)

In order to avoid the flash, we can replace useEffect with useLayoutEffect. `useLayoutEffect` functions exactly the same as `useEffect`, but runs before the DOM has been painted.

>[codepen](https://codepen.io/GreenSock/pen/XWRBbYZ)

`useLayoutEffect` is especially useful when you need to make DOM measurements, so we highly recommend it when using our [ScrollTrigger](https://greensock.com/docs/v3/Plugins/ScrollTrigger) and [FLIP](https://greensock.com/docs/v3/Plugins/Flip) plugins.

>More information about [useEffect vs useLayoutEffect](https://kentcdodds.com/blog/useeffect-vs-uselayouteffect).