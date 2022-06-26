---
title: "Vite 使用 env"
tag: 
- vite
---

##  Vite 使用 env
>- [Vite 文件：環境變量和模式＃環境變量](https://www.vitejs.net/guide/env-and-mode.html#env-variables)
>- [loading env variables in react app using vite](https://stackoverflow.com/questions/70883903/loading-env-variables-in-react-app-using-vite)
>- [How to use Environment Variables in Vite(React Template Example)](https://blog.ramadevsign.com/how-to-use-environment-variables-in-vite-react-template-example)

VITE_ 是必要前綴，API_KEY 是自訂變數名稱（或是使用 [envPrefix](https://www.vitejs.net/config/index.html#envprefix) 修改前綴）
```env
VITE_API_KEY=secret
```

```jsx
// 使用時用前面要加 import.meta.env.
const apiKey = import.meta.env.VITE_API_KEY
```

### 使用 process.env. 會出錯
![](https://i.imgur.com/tQ4MXVS.png)
會這樣