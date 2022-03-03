# data attribute：自訂 HTML 屬性
>[使用數據屬性(data attribute)](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Howto/Use_data_attributes)

在 HTML 上可以任意自訂 `data-*` 的屬性，使 JS 可以輕易訪問
```html
<article
  id="文章"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars">
...
</article>
```


## 如何用 JS 訪問
- `getAttribute()`
- `DOMStringMap` 的 `dataset`

```js
var article = document.querySelector('#文章');

// 記得原本用 - 連接的字要用 camelCase 拼
article.dataset.columns // "3"
article.dataset.indexNumber // "12314"
article.dataset.parent // "cars"
```


## 用 CSS z; 3jp4
#html #js #js/dom 