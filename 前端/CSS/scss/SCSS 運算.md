---
title: "SCSS 運算"
tag: 
- css/scss
---

##  SCSS 運算

除法
- `math.div(被除數, 除數)`
- `calc(被除數 / 除數)`
```scss
// 記得要匯入
@use "sass:math";

@for $i from 1 through $numberVariable {
  .col-#{$i} {
    width: math.div(100%, $grid-columns) * $i;
    flex: 1 0 0%;
  }
}
```

>[@for(SCSS)](@for(SCSS).md)