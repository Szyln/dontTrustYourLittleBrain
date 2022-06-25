---
title: "Netlify 部署後的 Router 問題"
tag: 
- vite
- publish/netlify
- routing
- js/react/route 
---

##  Netlify 部署後的 Router 問題
[Page Not Found Error on Netlify Reactjs React Router solved](https://dev.to/rajeshroyal/page-not-found-error-on-netlify-reactjs-react-router-solved-43oa)
[History pushstate and single-page apps](https://docs.netlify.com/routing/redirects/rewrites-proxies/#history-pushstate-and-single-page-apps)

>React Router handles routing on the client-side (browser) so when you visit the non-root page (e.g. `https://yoursite.netlify.com/login`), Netlify (server-side) does not know how to handle the route.  
>  
>_(As your routes are set up in the root level)._

[React Router(react-router-dom)](React%20Router(react-router-dom).md) 處理 client-side 的 Routing，但如果不是直接拜訪網站的 root 路徑的話，從 server-side 處理 route 的 Netlify 會沒辦法辨識

```shell
# 新增 public/_redirects 
/* /index.html 200
```


