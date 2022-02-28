# 取代 @import 的 @use, @forword
`@import` 的特性會全域污染，導致不同 `.sass` / `.scss` 檔案中若有命名重複的變數會撞名
官方建議使用 `@use`, `@forword` 取代
## @import
```scss
@import `font`;
@import `color`;
```

## 用 @use 取代
- 要注意 `@use` 的狀況不會全域污染，所以使用時要標註路徑
- 可以使用 `as` 來簡化路徑稱呼
- `as *` 可以直接簡化不用寫路徑

```scss
@use `font` as f;
@use `abstract` as *;

h1 {
	font-size: f.$font-size-1;
}


```
## 集中匯出：@forword

```scss
// abstract/index.scss
@forword `../abstract/font`;
@forword `../abstract/color`;
```
```scss
// 也可以 as * ，這樣使用起來就跟 import 非常類似
@use `../abstract`;

h1 {
	font-size: abstract.$font-size-1;
}
```