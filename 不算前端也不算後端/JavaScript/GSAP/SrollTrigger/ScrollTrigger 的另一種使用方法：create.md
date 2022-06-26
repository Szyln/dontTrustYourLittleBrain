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