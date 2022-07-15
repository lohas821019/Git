# git 指令

Git 是什麼？
一種版本控制的工具

GitHub 是什麼？
一個網站。讓你放原始碼 (Source Code) 的空間，如果只需要放公開的程式碼，可以免費使用


![image](https://user-images.githubusercontent.com/101848874/160342775-316e1e98-d4fd-4281-bf48-f297feb7d8fb.png)


```
git config --global user.name
git config --global user.email

git config --list
git status 

git remote -v #查詢 origin url  ，確認目前Git遠端伺服器網址
git remote add origin "repo的位置"

git remote set-url "別名" "url"  #更換Git遠端伺服器位網址
git remote add "別名" "url"

git branch "分支名稱" #產生分支
git checkout "分支"
git pull = git fetch(查看) + git merge (同步分支)

git push --set-upstream origin "分支"
git commit -am "message" (同時 add 以及commit)
git clone --branch <branchname> <remote-repo-url> 拉取特定分支
```

![/git_command_list.png](/resources/git_command_list.png)
[參考網站](https://www.mit.edu/~amidi/teaching/data-science-tools/study-guide/engineering-productivity-tips/#working-with-bash)


<br>

# Git flow 

![/git_command_list.png](/resources/flow.png)

Master 分支:

主要是用來放穩定、隨時可上線的版本。這個分支的來源只能從別的分支合併過來，開發者不會直接 Commit 到這個分支。因為是穩定版本，所以通常也會在這個分支上的 Commit 上打上版本號標籤。

Develop 分支:

這個分支主要是所有開發的基礎分支，當要新增功能的時候，所有的 Feature 分支都是從這個分支切出去的。而 Feature 分支的功能完成後，也都會合併回來這個分支。

Hotfix 分支:

當線上產品發生緊急問題的時候，會從 Master 分支開一個 Hotfix 分支出來進行修復，Hotfix 分支修復完成之後，會合併回 Master 分支，也同時會合併一份到 Develop 分支。

為什麼要合併回 Develop 分支？如果不這麼做，等到時候 Develop 分支完成並且合併回 Master 分支的時候，那個問題就又再次出現了。

那為什麼一開始不從 Develop 分支切出來修？因為 Develop 分支的功能可能尚在開發中，這時候硬是要從這裡切出去修再合併回 Master 分支，只會造成更大的災難。

Release 分支:

當認為 Develop 分支夠成熟了，就可以把 Develop 分支合併到 Release 分支，在這邊進行算是上線前的最後測試。測試完成後，Release 分支將會同時合併到 Master 以及 Develop 這兩個分支上。Master 分支是上線版本，而合併回 Develop 分支的目的，是因為可能在 Release 分支上還會測到並修正一些問題，所以需要跟 Develop 分支同步，免得之後的版本又再度出現同樣的問題。

Feature 分支:

當要開始新增功能的時候，就是使用 Feature 分支的時候了。Feature 分支都是從 Develop 分支來的，完成之後會再併回 Develop 分支。

[參考網站](https://gitbook.tw/chapters/gitflow/why-need-git-flow)
