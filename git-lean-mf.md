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

git checkeout -b 'dev'

$ git branch dev
$ git checkout dev

git add * && git commit -m "comm banch dev"

git checkout master
git merge dev
git branch -d dev

git fetch origin master
git log -p master ..orgin/master
git merge origin/master

git pull

### 自定义命令

$ git config --global alias.st status