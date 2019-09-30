# git命令练习和git笔记
> 为了便于以后巩固复习git命令

## git配置
$ git config --global user.name "Your Name"  
$ git config --global user.email "email@example.com"  
$ ssh-keygen -t rsa -C "youremail@example.com" 创建SSH Key  

## git基础命令
$ git init 把当前目录变成git  
$ git add readme.txt 文件添加到仓库  
$ git rm test.txt 从仓库中删除文件  
$ git commit -m "wrote a readme file" 文件提交到仓库（引号内为注释）  
$ git commit --amend --no-edit 文件提交与上一个提交合并，并以上一个提交为注释  
$ git commit -am "change 3 in dev" 相当于add+commit(untrack的文件不提交)  
$ git status 命令可以让我们时刻掌握仓库当前的状态  
$ git status -s 简单显示状态  
$ git diff 查看unstaged（如果想要查看这次还没 add (unstaged) 的修改部分 和上个已经 commit 的文件有何不同）  
$ git diff --cached 查看staged  
$ git diff HEAD -- readme.txt 查看staged和unstaged(命令可以查看工作区和版本库里面最新版本的区别)  

## git历史和回退版本
$ git log --pretty=oneline 查看穿梭前历史，单行显示  
$ git log --oneline --graph 查看穿梭前历史，单行显示，并显示分支  
$ git reflog 查看所有历史  
$ git reset  从staged回退到unstaged  
$ git reset --hard HEAD^ 回退上个版本  
$ git reset --hard HEAD~10 回退上10个版本  
$ git checkout -- readme.txt 把readme.txt文件在工作区的修改全部撤销  
$ git checkout 0b5ad7e -- readme.txt 把readme.txt文件回撤到0b5ad7e历史  
$ git reset HEAD file可以把暂存区的修改撤销掉  

## 分支命令
$ git checkout -b dev 创建并切换分支到dev  
$ git branch 命令查看当前分支  
$ git branch -d dev 删除dev分支  
$ git checkout master 切换回master分支  
$ git merge dev 用于合并指定分支到当前分支.会采用默认的 Fast forward 格式进行 merge, 这样 merge 的这次操作不会有 commit 信息. log 中也不会有分支的图案.  
$ git merge --no-ff -m "keep merge info" dev  我们可以采取 --no-ff 这种方式保留 merge 的 commit 信息.  
$ git stash 暂存修改  
$ git stash list 显示暂存中未恢复的列表  
$ git stash pop 从暂存中恢复  

## 远程库操作
$ git remote add origin git@server-name:path/repo-name.git 要关联一个远程库  
$ git push -u origin master 第一次推送master分支的所有内容  
$ git push origin master 推送最新修改  
$ git clone git@server-name:path/repo-name.git  
