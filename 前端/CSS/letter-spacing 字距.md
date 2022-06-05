---
title: "letter-spacing 字距"
tag: 
- 
---
# letter-spacing
>[mdn](https://developer.mozilla.org/ja/docs/Web/CSS/letter-spacing)
```css
letter-spacing: normal;
letter-spacing: <length>;
```

## 需注意
>[Letter-spacing wrong text center alignment](https://stackoverflow.com/questions/21612058/letter-spacing-wrong-text-center-alignment)
![](https://i.imgur.com/HRucc0W.png)

`letter-spacing` 顯示上是加在字的尾端的，如果是需要置中的狀況，會導致字偏左，可以補上 `text-indent`達到置中效果
```css
text-indent: <跟 letter-spacing 相同的值>;
```
#css 