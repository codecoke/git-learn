# git lean mf

## git  init
## git add read.txt
## git status
## git commit -m "edit redame.txt"
## git log --pretty=oneline
## git --hard HEAD^^
## git --hard HEAD 6d2007
## git reflog
## git diff HEAD -- readme.txt #查看工作区文件变化

git diff 是工作区和暂存区的对比
git diff -- cached 是暂存区和分支的对比
git diff HEAD -- readme.txt  工作区和分支的对比


Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

### 查看分支

$ git log --graph --pretty=oneline --abbrev-commit

Creating a new branch is quick AND simple.

### 合并分支 no-ff

$ git merge --no-ff -m "merge with no-ff" dev

合并分支时，加上--no-ff参数就可以用普通模式合并，
合并后的历史有分支，能看出来曾经做过合并，
而fast forward合并就看不出来曾经做过合并

git stash
git stash list
git stash pop

git stash apply stash@{0}
git stash drop stash@{0}

### 删除分支
git branch -d feature1
git branch -D feature1  #强制删除

get remote -v

$ git checkout -b dev origin/dev

设置和远程分支链接 
$ git branch --set-upstream dev origin/dev 废弃

git branch --set-upstream-to=origin/<branch> dev

$ git pull 抓


因此，多人协作的工作模式通常是这样：

首先，可以试图用git push origin branch-name推送自己的修改；

如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

如果合并有冲突，则解决冲突，并在本地提交；

没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。


命令git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id；

git tag -a <tagname> -m "blablabla..."可以指定标签信息；

git tag -s <tagname> -m "blablabla..."可以用PGP签名标签；

命令git tag可以查看所有标签。

小结

命令git push origin <tagname>可以推送一个本地标签；

命令git push origin --tags可以推送全部未推送过的本地标签；

命令git tag -d <tagname>可以删除一个本地标签；

命令git push origin :refs/tags/<tagname>可以删除一个远程标签。


在git中如果想忽略掉某个文件，不让这个文件提交到版本库中，可以使用修改根目录中 .gitignore 文件的方法（如无，则需自己手工建立此文件）。这个文件每一行保存了一个匹配的规则例如：

# 此为注释 – 将被 Git 忽略

*.cs       # 忽略所有 .cs 结尾的文件
!ABC.cs    # 但 ABC.cs 除外
/BLL       # 仅仅忽略项目根目录下的 BLL 文件，不包括 subdir/BLL
build/     # 忽略 build/ 目录下的所有文件
doc/*.txt  # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
规则很简单，不做过多解释，但是有时候在项目开发过程中，突然心血来潮想把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效，原因是.gitignore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。那么解决方法就是先把本地缓存删除（改变成未track状态），然后再提交：

git rm -r --cached .
git add .
git commit -m 'update .gitignore'

### 自定义命令
git config --global alias.st status
git config --global unset alias.st

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

### 中文文件名乱码

$git config –global core.quotepath false
