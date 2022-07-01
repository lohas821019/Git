# git 指令

Git 是什麼？
一種版本控制的工具

GitHub 是什麼？
一個網站。讓你放原始碼 (Source Code) 的空間，如果只需要放公開的程式碼，可以免費使用


![image](https://user-images.githubusercontent.com/101848874/160342775-316e1e98-d4fd-4281-bf48-f297feb7d8fb.png)


```
git config --list
git status 

git remote -v #查詢 origin url  ，確認目前Git遠端伺服器網址
git remote set-url "別名" "url"  #更換Git遠端伺服器位網址
git remote add "別名" "url"

git branch "分支名稱" #產生分支
git checkout "分支"
git pull = git fetch(查看) + git merge (同步分支)

git push --set-upstream origin "分支"
git commit -am "message" (同時 add 以及commit)
git clone --branch <branchname> <remote-repo-url> 拉取特定分支
```
123
![/git_command_list.png](/Git/git_command_list.png)

參考網站:

https://www.mit.edu/~amidi/teaching/data-science-tools/study-guide/engineering-productivity-tips/#working-with-bash
