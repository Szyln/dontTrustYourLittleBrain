---
title: "button 的樣式 reset"
tag: 
- css/reset
---

##  button 的樣式 reset
>[Remove the complete styling of an HTML button/submit](https://stackoverflow.com/questions/2460100/remove-the-complete-styling-of-an-html-button-submit)

```css
button, input[type="submit"], input[type="reset"] {
	background: none;
	color: inherit;
	border: none;
	padding: 0;
	font: inherit;
	cursor: pointer;
	outline: inherit;
}
```