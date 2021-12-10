# push 
在 push 之前，git 只有在本機的 git 運作，
若資料要儲存在網路上，則需要連到遠端的 repo
需完成
- git remote add 
- git push	

有兩種方法
- [[push & clone#現存本機 repo 加入到遠端 repo]]
- [[push & clone#遠端新增數據庫，抓下來用]]


## 現存本機 repo 加入到遠端 repo
1. 在 github 新增 repo（遠端）
2. 為已存在的本機 repo 連上遠端 repo，並新增 branch
```
git remote add <遠端數據庫簡稱> <url>
git branch -M main
```
3. 檢查是否連上，觀看遠端數據庫列表
```
git remote
```
4. push 資料上去
```
git push -u <遠端數據庫簡稱> main
```
`-u`: upstream



## 遠端新增數據庫，抓下來用
由於會自動綁定好，可以視為另一種取得 remote repo 的方法

### 順序
1. github 新增 repo(remote) 
2. 新增 readme 等檔案
3. clone 到本機
```
git clone <url>
```
4. 開始編輯專案，不需重新執行 `git init`

## 其他指令
-   觀看遠端數據庫列表(包含 url)：`git remote -v`

#git