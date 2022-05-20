---
title: "資料大於、小於、不等於、包含：_gte, _lte, _ne, _like"
tag: 
- js/api
---

##  資料大於、小於、不等於、包含：_gte, _lte, _ne, _like
- `_gte`：>=
- `_lte`：<=
- `_ne`：!==
- `_like`：filter，包含字串 ^3bd4c3

```
GET /posts?views_gte=10&views_lte=20
```
```
GET /posts?title_like=server
```