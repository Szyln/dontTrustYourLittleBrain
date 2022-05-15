---
title: "@for(SCSS)"
tag: 
- css/scss
---

##  @for(SCSS)
```scss
// i 會重複執行 $numberVariable 次
@for $i from 1 through $numberVariable {
  .col-#{$i} {
    width: 100% / $grid-columns * $i;
    flex: 1 0 0%;
  }
}
```

