# Git常用命令
### 删除
-   `find . -name ".git" | xargs rm -Rf ` —— 删除整个git仓库



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
