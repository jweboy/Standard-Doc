# Git常用命令
### 删除整个仓库
-   `find . -name ".git" | xargs rm -Rf ` —— 删除整个git仓库
-
### 添加
- `git add [fileName]`
- `git add -f [fileName]`强制添加

### 打印log
-   `git log`显示提交日志(从近到远)
-   `git log --pretty=oneline`单行显示日志
-   `git log --graph --pretty=oneline --abbrev-commit`

### 合并
-   `git merge`删除分支不保留分支历史
-   `git merge --no-ff -m "提交的注释" [branch]` 禁用`Fast forward`模式,`-m`添加新的commit描述,删除分支保留分支历史

### 存储
-   `git stash` 把当前工作区域存储起来
-   `git stash list` 查看所有存储的工作区
-   `git stash apply stash@{0}` 恢复存储的工作区
-   `git stash pop` 删除存储的工作区
### 分支
-   `git branch -d [branch]` 删除分支
-   `git branch -D [branch]` 强制删除分支

### 远程
-  `git remote` 查看远程库信息
-   参数功能：
- `git pull [origin] [branch]`取回远程更新,第一次取回加上远程名和分支名，其后直接使用`git pull`
-     `-v` 查看远程库详细信息
- `git push [origin] [branch]`远程推送
- `git checout -b [local-branch] [origin]/[origin-branch]` 在本地创建与远程对应的分支(名称最好一致)
-   "no tracking information" 表示本地与远程分支未建立链接关系
- `git branch --set-upsteam [branch] [origin]/[branch]`将本地分支与远程分支建立连接

### ignore
- `git check-ignore -v [fileName]` 检查文件是否在忽略规则中



### 标签
- `git tag [name]` 新建一个标签，默认是HEAD,也可以指定一个 commit id
- `git tag -a [name] -m "commit content" [commit id] ` 指定标签内容
- `git tag -s [name] -m "commit content" [commit id] `用PGP签名标签
- `git tag` 查看所有标签
- `git show [name]` 查看标签说明
- `git tag -d [name]` 删除本地标签
- `git push [origin] [name]` 推送某个标签到远程
- `git push [origin] --tags` 推送所有标签到远程
- `git push [origin] :refs/tags/[name]` 删除远程标签


### 初始化一个空仓库,并绑定远程仓库
    cd git\ branch
    git init
    git remote add origin git@github.com:jweboy/Git-Branch-Test.git
    git remote
    git pull origin master / git fetch origin

### 仓库添加修改文件，上传至远程仓库
    git add . / git add -p
    git status
    git commit -m "commit content"
    git push -u origin master
