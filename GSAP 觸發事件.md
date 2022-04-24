#### 觸發事件
- onUpdate
- onComplete
- onStart

```js
gsap.to(myObject, {duration: 2, rotation: 360, 
	onUpdate: function() { 	// 還有其他觸發事件像是 onStart, onComplete
	console.log(myObject.rotation)
}})
```
