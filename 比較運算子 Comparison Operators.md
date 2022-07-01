## 比較運算子 Comparison Operators
[優先性 Operator Precedence](優先性%20Operator%20Precedence.md): left-to-right

- `>=`, `<=`, `>`, `<`, `!==`, `!=`
- `==`：[資料型別](資料型別.md) 可不同，但值相同
- `===`：完全相同

> `=`：==宣告用非比較==


>[Coercion 造成的意外](Coercion%20造成的意外.md)：盡量使用越嚴謹的 === 越好
```js
NaN == NaN // false
undefined === null // false
undefined == null // true
+0 === -0 // true  
```


> object 與 array 判斷是否等於，看的會是其參考地址是否相等。