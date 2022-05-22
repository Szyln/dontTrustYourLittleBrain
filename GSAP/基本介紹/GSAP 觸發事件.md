#### 觸發事件
```js
gsap.to(myObject, {duration: 2, rotation: 360, 
	onUpdate: function() { 	// 還有其他觸發事件像是 onStart, onComplete
	console.log(myObject.rotation)
}})
```
- onUpdate
- onComplete
- onStart

|觸發事件|描述|
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `onComplete`              | 可以設定一個「動畫結束」時執行的函式 			                                                                                                                         |
| `onRepeat`                | 動畫重複時（需設定動畫為 non-zero repeat)			                                |
| `onReverseComplete`       | reached its beginning again from the reverse direction (excluding repeats). 			                                                        |
| `onStart`                 | 動畫開始時 (restart 之後也會執行) 			 |
| `onUpdate`                | 動畫更新時 (on each "tick" that moves its `playhead`). 			                                                                                |
| `onCompleteParams`        | 給 `onComplete` 設定的函式帶入的參數 <br >範例：` gsap.to(".class", {x:100, onComplete:myFunction, onCompleteParams:["param1", "param2"]});`     |
| `onRepeatParams`          | 給 `onReapeate`（同上）                                                                                                                       |
| `onReverseCompleteParams` | 給 `onReverseComplete`（同上）                                                                                                             |
| `onStartParams`           |  				給 `onStart`（同上）                                                                                                                      |
| `onUpdateParams`          |         給 `onUpdate`（同上）                                                                                                                                                                  |

