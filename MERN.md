---
title: "MERN"
tag: 
- js/mern
---
# MERN
>- [React. js + Node. js + Express + MongoDB example: MERN stack CRUD App](https://www.bezkoder.com/react-node-express-mongodb-mern-stack/)
>- [MERN Stack Explained](https://www.mongodb.com/mern-stack)

專案會分成
- 前端 [[React]] 
- 後端 [Express.js](後端/Express.js/Express.js.md), [Mongoose](後端/Database/noSQL/Mongoose/Mongoose.md), [MongoDB Atlas, Passport.js, OAuth](後端/MongoDB%20Atlas,%20Passport.js,%20OAuth/MongoDB%20Atlas,%20Passport.js,%20OAuth.md)

然後用 API 串起來

## MERN 前端
- [Vite](React/環境/Vite/Vite.md)
## MERN 後端
- [MERN 後端安裝](MERN%20後端安裝.md)
- [[cors]]：同時跑前後端伺服器

## 架構
```shell
|- server
|	|- config # passport.js
|	|- models	# mongoose models
|	|- routes	
|- .env			# 用插件 code runner 跑會跳錯
|- index.js
|- validation.js
```
### server/config


#js/mern 