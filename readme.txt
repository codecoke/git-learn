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
Creating a new branch is quick AND simple.

