## 上傳有 gulp 管理的 git 檔案

[[Repository]]
```
git init
git add
git
```
在該資料夾執行 git 指令
並 push 到 github
```
git remote 
add origin [GitHub Repositories Url]
git push -u origin main
// 僅限第一次輸入，往後只需要輸入 git push
```

## 部屬與更新
生產模式
```
gulp build
```
客戶端看到的畫面部屬 gh-pages（頁面顯示可能要等一下
```
gulp deploy  
```
客戶只會看到 dist 裡（編譯後）的檔案

## [[Git/基礎/Github Pages]] 取得靜態網頁
branch 要選 gh-pages


## 後續更新
### 客戶端
重複[[GULP 的 Github 部屬#部屬與更新]]
### 程式端
add>commit>git push -u origin master

#gulp