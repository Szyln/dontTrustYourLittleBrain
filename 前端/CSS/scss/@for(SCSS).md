---
title: "@for(SCSS)"
tag: 
- css/scss
---

##  @for(SCSS)
```scss
@use "sass:math";
// i 會重複執行 $numberVariable 次
@for $i from 1 through $numberVariable {
  .col-#{$i} {
    width: math.div(100%, $grid-columns) * $i;
    flex: 1 0 0%;
  }
}
```


>[SCSS 運算](SCSS%20運算.md)