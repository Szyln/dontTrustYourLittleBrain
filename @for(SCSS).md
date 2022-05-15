---
title: "@for(SCSS)"
tag: 
- css/scss
---

##  @for(SCSS)
```scss
// 
@for $i from 1 through $grid-columns {
  .col-#{$i} {
    width: 100% / $grid-columns * $i;
    flex: 1 0 0%;
  }
}
```

