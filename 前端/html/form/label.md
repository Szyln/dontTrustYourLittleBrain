# label tag
- input 的標籤（不強制使用）
- 點擊 `label` 就會反白 `input`
- 不要把 placeholder 當 label 用
## 一組 label & input 的架構
```html
<!-- 用 div 包 -->
<div>
	<label for="myName">姓名</label>
	<input type="text" id="myName">
</div>
```
```html
<!-- 用 label 包 -->
<label for="myName">姓名
	<input type="text" id="myName">
</label>
```

若有 p tag 不要包在裡面

#form #html 