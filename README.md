## git设置

参照：https://segmentfault.com/a/1190000016269686

```
git config --global user.name "xxx"
git config --global user.email "xxx"
git config --list
git config --global --unset user.name
git config --global --unset user.email

ssh-keygen -t rsa -C "xxx"
ssh-add ~/.ssh/<github_id_rsa>

touch config
Host github 
HostName github.com 
User xxxx 
IdentityFile ~/.ssh/<github_id_rsa>
```



参照：https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

## 分支

- 查看所有分支(本地+远端) `git branch -a`
- 创建分支 `git branch <name>`
- 切换分支 `git checkout <name>`
- 创建➕切换分支 `git checkout -b <name>`
- 合并分支到当前分支 `git merge <name>`   `git merge --no-ff -m "xxx"<name>`
- 取远端分支到本地一个新分支 `git checkout -b <name> origin/<name>`
- 删除本地分支 `git branch -d <name>`   `git branch -D <name>`

## 查看历史

- `git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit`
- `git reflog`

## 工作区 暂缓区 分支

- 暂存工作区 `git stash`
- 恢复 删除暂存的内容 `git stash drop`
- 查看stash内容 `git stash list`

- 查看远程库信息 `git remote`    `git remote -v`
- 本地推送分支 `git push origin <name>`
- 删除远端分支 `git push origin --delete <name>`
- `git pull`
- 本地分支与远程分支关联`git branch --set-upstream <name> origin/<name>`
- 本地创建与远程对应的分支 `git checkout -b <name> origin/<name>`
- 工作区取消修改`git checkout -- <name>`
- 进到指定(HEAD HEAD^...)版本(git commit后) `git reset --hard xxxID`  
  soft参数的话会回退到之前的版本，但是保留当前工作区的修改 hard不保留
- 内容提交到暂缓区(git add后)取消修改的内容  1、 `git reset HEAD <name>`  2、`git checkout -- <name>`
- `git rm <name>`  `git commit -m "删除 xxxx"`



## 标签

 ```
git tag -a v0.1 -m ""
git tag 
git show <name>
git tag -d <name>
推送本地标签 git push origin <tagname>
推送全部为推送的本地标签 git push origin --tags
删除远程标签  git push origin :refs/tags/<tagname>
 ```

