# flexbox
> [Animated Flexbox Playground](https://codepen.io/osublake/full/dMLQJr)
-   [[flex-wrap]]: wrap-reverse;
-   flex:1 代表 flex-grow
-   ul > li > a > 字＋圖
```html
    <ul class="d-flex">
      <li>
        <a>AAAA</a>
      </li>
    </ul>
```
-   ul: d-flex, width
-   li: flex-1
-   a: d-block, padding（一致）, 連結的互動設定
-   img: d-block, m-auto

## 外容器與內容

### 容器
- [[d-flex]]
- flex-flow：
	- flex-direction：流向
	- flex-wrap：出血後是否換行
 - justify-content：分配每個內容的主軸寬度
- align-items：每個內容自有交錯軸內的定位（不影響內容物彼此）
- align-content： `flex-wrap` 設定後有效（交錯軸上出現其他內容），分配每個內容在交錯軸的寬度

### 內容
# flex
-  `flex-grow` 
-  `flex-shrink`
-  `flex-basis`
# align-self
# order


## flex 中 flex
如果需要多層次的內容，在內層再下 `flex`

## max-width
容器下 max-width
內容物的寬度下 %

---

![](https://i.imgur.com/DtbIkHM.png)

#css