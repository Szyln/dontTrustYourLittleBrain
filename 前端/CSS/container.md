---
title: "container"
tag: 
- css/scss/bs
---
## container
### 效果說明
```scss
.container {
	margin: 0 auto;		// 水中置中
	max-width: 60%; // 不出現 x 軸，要比螢幕寬度小
	padding: 0 10px // container 內容物不要貼死 container 邊框
	
	@media (max-width: 1080px) {
		max-width: 60%; // 螢幕寬度 1080px 以下都維持螢幕寬度的 60%
	}
	@media (max-width: 768px) {
		width: 100%; // 螢幕寬度 768px 以下都顯示為滿版（失去 container 效果）
		
	}
}
```
#### 水平置中
使用 margin left, right 都設定 `auto`（必須要設定 `width` 才會作用）

#### 非滿版
不同斷點有不同 width 設定（響應式）

`width` 的設定配合響應式必須：
- 使用 `max-width`：不會隨著螢幕寬度出現 x 軸
- `.container` 的 `max-width` 必須小於當下斷點的螢幕寬度：維持非滿版的樣式


### bootstrap 的響應式 container
bs 針對不同情況的 container 有不同的樣式可以設定
![](https://i.imgur.com/B6BHJHH.png)
### 用法
有些內容只有限定電腦版非滿版，更窄的就滿版了，那就也沒必要設定置中了
```scss
.container-lg {
  @media (max-width: 768px) {
  	width:100%; // 到達 md 就滿版
	padding: 0 10px // 還是有左右留白
  }
}
```

#### bs 內建的不夠，想客製化 container
```scss
```scss
// Source mixin
@mixin make-container($padding-x: $container-padding-x) {
  width: 100%;
  padding-right: $padding-x;
  padding-left: $padding-x;
  margin-right: auto;
  margin-left: auto;
}

// Usage
.custom-container {
  @include make-container();
}
```
