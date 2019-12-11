### learn github
#### 1.安装 git

+ $ git config --global user.name "Your Name"
+ $ git config --global user.email "email@example.com"

#### 2.创建版本库
+先在本地建一个文件夹，在此文件夹中打开git命令提示符界面，然后`$ git init`
+ `$ git add <file>`添加文件至仓库
+ `$ git commit -m "my first file"`提交文件至仓库
#### 3.基本操作
+ `$ git log`显示提交的日志历史
+ `$ git log --pretty=oneline`将日志线性化
+ `$ git relog`查看历史命令
+ `$ git reset --hard HEAD^`回退至上一版本
+ `$ git reset --hard HEAD~100`回退至上一百版本
+ `$ git reset HEAD file.txt`撤销file.txt缓存区的修改
+ `$ git status`查看状态
+ `$ git HEAD file.txt`比较工作区和缓存区
+ `$ git diff HEAD --file.txt`查看工作区和版本库里面最新版本的区别
+ `$ git checkout --file.txt`丢弃对文件file.txt的工作区的修改
+ 从版本库中删除文件：`$ git rm file.txt`
+ 提交删除:`$ git commit -m "remove file.txt"`
#### 4.分支管理
+ `$ git checkout -b fenzhi1`建立新分支
+ `$ git dranch`查看当前分支
+ `$ git checkout master`切换至master分支
+ `$ git switch -c new1`切换至新分支new1
+ `$ git switch master`切换至主分支
+ `$ git merge fenzhi1`将分支1与其母分支合并
+ `$ git branch -d fenzhi1`删除分支1
+ 查看分支图：`$ git log --graph --pretty=oneline --abbrev-commit`
+ 强制删除分支1：`$ git checkout -D fenzhi1`
+ 查看远程库信息：
+ `$ git remote`
+ `$ git remote -v`显示细节
+ 推送分支1至origin：`$ git push origin fenzhi1
+ 在本地创建与远程分支对应的分支：`$ git checkout -b fenzhi2 origin/fenzhi2`只管修改分支2，不时合并分支（git add然后git commit）
+ 若推送失败：`$ git pull`来抓取分支
+ 若抓取失败：
先`$ git branch --set-upstream-to=origin/fenzhi2 fenzhi2`建立本地分支和远程分支的关联，再抓取`$ git pull`,然后在解决了冲突后git commit并`$ git push origin fenzhi2`即可把本地未push的分叉提交历史整理成直线：`$ git rebase`

#### 总结：我认为git的作用大致分为以下几类:
+ 记录下文件的修改，在改动错误等需求下，可以根据记录的历史修改，将文件恢复至未修改前的某个适当的版本；
+ 建立新的分支，再对新的分支进行修改，当新的分支符合修改要求时，可合并分支，避免了直接改动源文件带来错误后的不易恢复性；
+ 可以多人共同对同一个文件进行开发，每个人建立不同的分支，并对自己负责的分支进行改动即可，最后商榷后合并为同至源文件，即可完成源文件的修改；
####特点：
+ 从分支进行修改时，大可不必为改动出错而烦恼；
+ 可以多人多个时间段多个地点对同一文件的不同部分进行修改；
+ 可以“后悔”，在修改出错时可以进行版本的回退；
+ 进行的分支修改情况对组员透明，方便其他人理解。