# flexbox

-   [Animated Flexbox Playground](https://codepen.io/osublake/full/dMLQJr)
-   flex-wrap: wrap-reverse;
-   flex:1 代表 flex-grow
-   ul > li > a > 字＋圖

-   ul: d-flex, width
-   li: flex-1
-   a: d-block, padding（一致）, 連結的互動設定
-   img: d-block, m-auto

## 外容器與內容
![](https://i.imgur.com/DtbIkHM.png)
### 外容器
- `display: flex`
- `flex-flow`
    - `flex-direction`
    - `flex-wrap`
- `justify-content`
- `align-items`
- `align-content`

### 內容物
- `flex`
    -  `flex-grow` 
    -  `flex-shrink`
    -  `flex-basis`
- `align-self`
- `order`

## 主軸與交錯軸
- 主軸：跟其他兄弟姊妹搶空間
    - `justify-content`
- 交錯軸：你的人生你自己可以決定
    - `align-items`
    - 兄弟姊妹半路殺出來干擾你的人生：`wrap`
        - `align-content`：再跟他們搶人生

## flex 中 flex
如果需要多層次的內容，在內層再下 `flex`

## max-width
容器下 max-width
內容物的寬度下 %

#css