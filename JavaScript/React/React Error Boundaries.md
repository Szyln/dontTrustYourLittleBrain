---
title: "React Error Boundaries"
tag: 
- js/react
---
## React Error Boundaries
>[Failing Gracefully with React Error Boundary](https://youtu.be/hszc3T0hdvU)
### 為什麼需要
- 專案變複雜，錯誤訊息會從各種來源進來
- 可能會呼叫根本不存在的 function 導致錯誤訊息
- Uncaught error 導致網頁全部停止

### 使用效果
將可能會產生錯誤訊息的元件用 error boundary 包起來，讓錯誤訊息只在這個區塊中顯現，而不停止網頁運作

### npm 
[react-error-boundary](https://www.npmjs.com/package/react-error-boundary)