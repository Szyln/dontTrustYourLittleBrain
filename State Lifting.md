# State Lifting
當元件一多的時候，會遇到需要跨元件共享同一個資料的狀況

```
<App />
|		|- props:
|		|- state: input, message
|- <Create />
|			|- props:
|			|- state: input, message
|- <Info />
|			|- props: X
|			|- state: X
```
```jsx
const Create = () =>
```