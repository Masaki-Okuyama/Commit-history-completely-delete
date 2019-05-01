# Commit-history-completely-delete
特定のファイルのコミット履歴を完全に削除する方法  

GitHubにパスワードをのせたファイルをアップしてしまった時にコミット履歴を削除したときのメモ。  
参考:[ktx2207](https://gist.github.com/ktx2207/3167fa69531bdd6b44f1)氏  
### ファイルを削除
```
$ git filter-branch -f --index-filter 'git rm --ignore-unmatch ファイル名' HEAD
```
### reflogを削除
```
$ git reflog expire --expire=now --all
```
### git gcを実行
```
$ git gc --aggressive --prune=now
```
### git push --forceを実行
```
$ git push --force origin master
```
