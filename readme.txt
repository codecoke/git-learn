# git lean mf

## git  init
## git add read.txt
## git status
## git commit -m "edit redame.txt"
## git log --pretty=oneline
## git --hard HEAD^^
## git --hard HEAD 6d2007
## git reflog
## git diff HEAD -- readme.txt #�鿴�������ļ��仯

git diff �ǹ��������ݴ����ĶԱ�
git diff -- cached ���ݴ����ͷ�֧�ĶԱ�
git diff HEAD -- readme.txt  �������ͷ�֧�ĶԱ�


Git��������ʹ�÷�֧��

�鿴��֧��git branch

������֧��git branch <name>

�л���֧��git checkout <name>

����+�л���֧��git checkout -b <name>

�ϲ�ĳ��֧����ǰ��֧��git merge <name>

ɾ����֧��git branch -d <name>

### �鿴��֧

$ git log --graph --pretty=oneline --abbrev-commit

Creating a new branch is quick AND simple.

### �ϲ���֧ no-ff

$ git merge --no-ff -m "merge with no-ff" dev

�ϲ���֧ʱ������--no-ff�����Ϳ�������ͨģʽ�ϲ���
�ϲ������ʷ�з�֧���ܿ��������������ϲ���
��fast forward�ϲ��Ϳ����������������ϲ�

git stash
git stash list
git stash pop

git stash apply stash@{0}
git stash drop stash@{0}

### ɾ����֧
git branch -d feature1
git branch -D feature1  #ǿ��ɾ��

get remote -v

$ git checkout -b dev origin/dev

���ú�Զ�̷�֧���� 
$ git branch --set-upstream dev origin/dev ����

git branch --set-upstream-to=origin/<branch> dev

$ git pull ץ


��ˣ�����Э���Ĺ���ģʽͨ����������

���ȣ�������ͼ��git push origin branch-name�����Լ����޸ģ�

�������ʧ�ܣ�����ΪԶ�̷�֧����ı��ظ��£���Ҫ����git pull��ͼ�ϲ���

����ϲ��г�ͻ��������ͻ�����ڱ����ύ��

û�г�ͻ���߽������ͻ������git push origin branch-name���;��ܳɹ���

���git pull��ʾ��no tracking information������˵�����ط�֧��Զ�̷�֧�����ӹ�ϵû�д�����������git branch --set-upstream branch-name origin/branch-name��

����Ƕ���Э���Ĺ���ģʽ��һ����Ϥ�ˣ��ͷǳ��򵥡�


����git tag <name>�����½�һ����ǩ��Ĭ��ΪHEAD��Ҳ����ָ��һ��commit id��

git tag -a <tagname> -m "blablabla..."����ָ����ǩ��Ϣ��

git tag -s <tagname> -m "blablabla..."������PGPǩ����ǩ��

����git tag���Բ鿴���б�ǩ��

С��

����git push origin <tagname>��������һ�����ر�ǩ��

����git push origin --tags��������ȫ��δ���͹��ı��ر�ǩ��

����git tag -d <tagname>����ɾ��һ�����ر�ǩ��

����git push origin :refs/tags/<tagname>����ɾ��һ��Զ�̱�ǩ��


��git���������Ե�ĳ���ļ�����������ļ��ύ���汾���У�����ʹ���޸ĸ�Ŀ¼�� .gitignore �ļ��ķ��������ޣ������Լ��ֹ��������ļ���������ļ�ÿһ�б�����һ��ƥ��Ĺ������磺

# ��Ϊע�� �C ���� Git ����

*.cs       # �������� .cs ��β���ļ�
!ABC.cs    # �� ABC.cs ����
/BLL       # ����������Ŀ��Ŀ¼�µ� BLL �ļ��������� subdir/BLL
build/     # ���� build/ Ŀ¼�µ������ļ�
doc/*.txt  # ����� doc/notes.txt �������� doc/server/arch.txt
����ܼ򵥣�����������ͣ�������ʱ������Ŀ���������У�ͻȻ��Ѫ�������ĳЩĿ¼���ļ�������Թ��򣬰�����������������ֲ�δ��Ч��ԭ����.gitignoreֻ�ܺ�����Щԭ��û�б�track���ļ������ĳЩ�ļ��Ѿ��������˰汾�����У����޸�.gitignore����Ч�ġ���ô������������Ȱѱ��ػ���ɾ�����ı��δtrack״̬����Ȼ�����ύ��

git rm -r --cached .
git add .
git commit -m 'update .gitignore'

### �Զ�������
git config --global alias.st status
git config --global unset alias.st

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

### �����ļ�������

$git config �Cglobal core.quotepath false
