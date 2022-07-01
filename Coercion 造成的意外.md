### Coercion 造成的意外
>[使用不同比較運算子得到的結果](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#a_model_for_understanding_equality_comparisons)

>[Coercion 強迫](Coercion%20強迫.md)

所以建議使用 `===`, `!==` >>>>>> `==`, `<=`, `>=` > 直接用 `<`, `>`
```js
console.log(3 < 2 < 1) // true! why?

// 拆解長這樣
3 < 2			 // false
false < 1  // false 被 coersion 成 0
0 < 1			 // true!

```