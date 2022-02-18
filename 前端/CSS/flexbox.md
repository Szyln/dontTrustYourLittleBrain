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
# display: flex
內容取消 inline 設定
# flex-flow
- flex-direction：流向
- flex-wrap：出血後是否換行

# justify-content
內容物互搶空間
# align-items
內容物自己空間的規劃
# align-content

- 主軸：跟其他兄弟姊妹搶空間
    - `justify-content`
- 交錯軸：你的人生你自己可以決定
    - `align-items`
    - 兄弟姊妹半路殺出來干擾你的人生：`wrap`
        - `align-content` ：再跟他們搶人生
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