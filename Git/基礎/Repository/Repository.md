# Respository 
```
git init
git add
git status
git commit -m "填寫這個 commit 的訊息"
git log
```

在[[4.Working Tree]]中 Respository 分為兩種
- 本機
- 遠端 (Github, Bitbucket)

## 本機 Repository
- [[初始化(git)]]
- Track

## Track and Stage
```
git add index.html
```
```
git add .
```


新增資料在 respository 之後，需要再 track 這個檔案，使他家入[[4.Working Tree]]的 staging area （索引）裡

### git status
檢查目前狀態
````
git status
````

## Commit
staged 後就可以是看看 commit 功能囉
```
git commit -m "<填寫版本資訊>"
```

## 查更新記錄 log
```
git log
```


## .gitignore
一個神秘的小檔案
裡面可以輸入不想要被 git 偵測的檔案
```
log.txt
justForTest.html

```
#git