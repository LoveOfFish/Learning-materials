git中的版本库又叫仓库，就是用来存放文件的

| Git命令                                                      | 作用                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| git init                                                     | 在某个目录下执行git init，就会把这个目录变成一个Git仓库，即Git可以管理这个目录(其中会生成.git目录，这个目录不要乱改，因为这个目录是Git用来跟踪管理仓库的) |
| git add filename                                             | 把名为filename的文件添加到暂存区中，也可以直接把一个或者多个目录添加到暂存区中 |
| git config --global user.name "Your Name"                    | 设置用户名（用于辨识身份）                                   |
| git config --global user.email "email@example.com"           | 设置邮件地址（用于辨识身份）                                 |
| git commit -m "message"                                      | 把暂存区中的文件提交到本地仓库中，-m选项是为了填写提交说明，用于以后查看 |
| git status                                                   | 查看当前工作区和暂存区的状态                                 |
| git diff                                                     | 查看当前工作区修改了哪些内容                                 |
| git log                                                      | 查看日志，可以看到以前的提交信息                             |
| git log --pretty=oneline                                     | 查看日志，只查看一部分信息                                   |
| git reset --hard HEAD^                                       | 回退上一个版本                                               |
| git reset --hard HEAD~5                                      | 回退到之前的第五个版本                                       |
| git reflog                                                   | 查看命令历史                                                 |
| git restore --staged <file>                                  | 在暂存区中删除file文件                                       |
| git diff HEAD -- readme.txt                                  | 查看工作区和版本库里面最新版本的区别                         |
| git checkout --  <file>                                      | 在工作区中撤销对file文件的修改，就是让这个文件回到最近一次`git commit`或`git add`时的状态 |
| git restore <file>                                           | 在工作区中撤销对file文件的修改，就是让这个文件回到最近一次`git commit`或`git add`时的状态 |
| git restore --staged <file>                                  | 把暂存区的修改撤销掉（unstage），重新放回工作区              |
| git reset HEAD <file>                                        | 把暂存区的修改撤销掉（unstage），重新放回工作区              |
| git rm test.txt                                              | 从版本库中删除，需要再执行git commit -m "message"提交这一操作 |
| git remote add origin git@github.com:LoveOfFish/learngit.git | 把本地仓库关联到远程仓库，远程仓库默认名字为origin，这个可以更改，后面git@...是你要关联的远程仓库，关联一个远程库时必须给远程库指定一个名字 |
| git push -u origin master                                    | 把本地的master分支推送到远程的origin仓库，origin是你给起的仓库名，方便我们以后使用这个仓库,-u参数是为了推送时进行关联，关联之后就可以不加-u参数了 |
| git push origin master                                       | 把本地`master`分支的最新修改推送至GitHub                     |
| git remote -v                                                | 查看远程库信息                                               |
| git remote rm origin                                         | 解除了本地仓库和远程仓库origin的绑定关系                     |
| git branch dev                                               | 创建名为dev的分支                                            |
| git checkout dev                                             | 切换到名为dev的分支                                          |
| git checkout -b dev                                          | 创建并切换到名为dev的分支                                    |
| git branch                                                   | 查看所有分支，分支前面带有*号的表示是当前的分支              |
| git merge dev                                                | 把名为dev的分支合并到当前分支中                              |
| git branch -d dev                                            | 删除名为dev的分支                                            |
| git switch -c dev                                            | 创建并切换到名为dev的分支                                    |
| git switch master                                            | 切换到已有的master分支                                       |
| git log --graph --pretty=oneline --abbrev-commit             |                                                              |
| git stash                                                    | 把当前工作现场“储藏”起来，等以后恢复现场后继续工作;需要`git stash`命令保存现场，才能从dev分支切换到master分支。 |
| git stash list                                               |                                                              |
| git stash pop                                                | 恢复工作现场，同时删除stash的内容                            |
| git stash apply                                              |                                                              |
| git stash drop                                               |                                                              |
| git stash apply stash@{0}                                    | 恢复指定的stash                                              |
| git cherry-pick 4c805e2                                      | 把4c805e2这一次所做的修改合并到（复制到）dev上               |
| git branch -D dev                                            | 丢弃一个没有被合并过的分支,强行删除                          |
| git remote                                                   | 查看远程库的信息                                             |
| git remote -v                                                | 查看远程库的信息                                             |
| git push origin dev                                          | 把本地的dev分支推送到远程的origin分支(也就是master分支)      |
| git branch --set-upstream-to <branch-name> origin/<branch-name> | 本地分支和远程分支建立链接关系                               |
| git checkout -b branch-name origin/branch-name               | 在本地创建和远程分支对应的分支                               |
| git tag v1.0                                                 | 打上一个名为v1.0的标签,默认标签是打在最新提交的commit上的    |
| git tag v0.9 f52c633                                         | 对f52c633的提交打上标签v0.9                                  |
| git tag                                                      | 查看标签                                                     |
| git show v0.9                                                | 查看标签为v0.9的信息                                         |
| git tag -a v0.1 -m "version 0.1 released" 1094adb            | 创建带有说明的标签，用`-a`指定标签名，`-m`指定说明文字       |
| git tag -d v0.1                                              | 删除名为v0.1的标签                                           |
| git push origin v1.0                                         | 推送名为v1.0的标签到远程                                     |
| git push origin --tags                                       | 一次性推送全部尚未推送到远程的本地标签                       |
| git push origin :refs/tags/v0.9                              | 删除远程标签,需要先删除本地仓库的标签                        |
|                                                              |                                                              |
|                                                              |                                                              |
| git config --global core.autocrlf false                      | 用于关闭Git自动转换换行符的警告：warning: LF will be replaced by CRLF in readme.txt.<br/>The file will have its original line endings in your working directory |



