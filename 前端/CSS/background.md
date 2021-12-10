# [background 屬性](https://developer.mozilla.org/ja/docs/Web/CSS/background)



## 概括寫法

沒有順序差別，只有 `<position>` / `<size> ` 要注意要寫在一起
可用0-1次：

-   `<attachment>`：fixed, local, scroll
-   `<image>`：url()
-   `<position>` / `<size> `：圖片比範圍小的時候好用的定位 / contain, cover, auto, `<length>`,<percentage>
-   `<repeat>`:repeat, space, round, no-repeat, repeat-x, repeat-y

只寫一個代表兩個都一樣，寫兩個的話第一個是 origin，第二個是 clip
- `<origin>`：padding-box, border-box (左上角起始座標)
- `<clip>`：padding-box, border-box （整個圖片的座標）
	
### [background-attachment](https://developer.mozilla.org/ja/docs/Web/CSS/background-attachment)

 相對 viewport 的固定方式

-   scroll
-   fixed
-   local

### background-size
設定長寬
設定填滿容器方式

-   contain：不填滿，以最大大小放入容器
-   cover：左右填滿
-   auto

### [background-position](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position)©

-   top, left, center, bottom
-   25% 75%（距左25%距上75%）

### [background-clip](https://developer.mozilla.org/ja/docs/Web/CSS/background-clip)

-   border-box：背景涵蓋 border 底下
-   padding-box：背景涵蓋 padding 底下（ bootstrap 用 col 要注意 ）
-   content-box：背景僅涵蓋在 content 底下

[How To - Aspect Ratio / Height Equal to Width](https://www.w3schools.com/howto/howto_css_aspect_ratio.asp)

[Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/mdn-css_properties_aspect-ratio)

  
	
	#css