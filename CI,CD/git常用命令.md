# git 常用命令

---

## git基本概念

![git主要组成][1]

> remote：指远程的仓库
repository：指本地的仓库
index：暂存区
workspace：本地工作区


## 常用的git命令

1. 克隆代码，下载一个项目以及其整个代码历史
    
    > git clone https://github.com/static-mkk/MyDocument.git


2. 增加、删除文件
    
    - git add filepath  : 把本地工作区的文件添加到暂存区，可以同时提交多个修改的文件，也可以是目录
    - git rm filepath 删除工作区文件，并将这个删除记录添加到暂存区，用于删除远程的文件
    - git mv file 修改文件名，并放入缓存区

3. 代码提交
    
    - git commit -m [message] :提交暂存区的内容到本地仓库，并指定message信息
    - git commit -a 提交工作区上次所有的变化
    - git commit -v 提交时显示所有diff信息

4. 分支

    - git branch 列出所有分支
    - git branch -r 列出所有远程分支 -a 列出所有本地和远程分支
    - git branch [分支名] 新建一个分支，但是仍然留在当前分支上 [-b 切换到新建的分支上]
    - git checkout [分支名] 切换到指定分支，并更新工作区
    - git merge [分支名] 合并制定分支名到当前分支
    - git branch -d [分支名] 删除本地指定分支
    - git push origin --delete [远程分支名] 删除远程分支
    
5. 查看信息

    - git status 查看变更的文件
    - git log 查看当前分支的版本历史
    - git diff 显示工作区和暂存区的差异

6. 远程同步
    
    - git fetch [远程仓库] 下载远程仓库所有变动
    - git remote -v 显示所有远程仓库
    - git remote add [远程仓库名] 添加一个新的远程仓库
    - git pull [远程仓库名] [本地仓库名] 把远程仓库中的内容更新到本地仓库
    - git push [远程仓库名] [本地仓库名] 上传本地指定分支到远程仓库
    - git push [remote] --force 强行推送当前分支到远程仓库，即使有冲突
    - git push [远程仓库名] --all 推送所有分支到仓库


## 更新fork的仓库

1. git remote add upstream  [远程仓库] 添加远程仓库
2. git remote -v 查看所有远程仓库
3. git fecth upstream 从源仓库同步代码
4. git merge upstream/[本地分支]合并源仓库的代码到本地分支
5. git pull origin [本地分支名] 拉去该分支远程仓库代码到本地分支
6. git push 向自己的远程仓库推送刚刚合并的代码
7. 最后提交PR










  [1]: http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120901.png