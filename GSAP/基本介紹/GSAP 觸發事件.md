---
title: "GSAP 觸發事件"
tag: 
- js/gsap/tween
---

##  GSAP 觸發事件
>[Tween](https://greensock.com/docs/v3/GSAP/Tween)：參照 Parameters --> vars --> 以下清單
```js
gsap.to(myObject, {duration: 2, rotation: 360, 
	onUpdate: function() { 	// 還有其他觸發事件像是 onStart, onComplete
	console.log(myObject.rotation)
}})
```

|觸發事件|描述|
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `onComplete`              | 可以設定一個「動畫結束」時執行的函式 			                                                                                                                         |
| `onStart`                 | 動畫開始時 (restart 之後也會執行) 			 |
| `onRepeat`                | 動畫重複時（需設定動畫為 non-zero repeat)			                                |
| `onUpdate`                | 動畫更新時 (on each "tick" that moves its `playhead`). 			                                                                                |
| `onReverseComplete`       | reached its beginning again from the reverse direction (excluding repeats). 			                                                        |

以上觸發事件若要帶入參數，可以用以下格式新增參數

```js
gsap.to(".class", {
	x:100,
	onComplete: myFunction,
	// on事件Params 即可帶入參數
+	onCompleteParams:["param1", "param2"]
});
```