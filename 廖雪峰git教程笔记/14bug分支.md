## bug分支

在dev版本上开发， 有人提交bug 102 说发布的master版本有bug,
需要暂停dev开发， 切换的主版本，创建bug102版本， 修复版本， 合并到master版本 。
然后回到dev版本。 
然后释放我们暂停的工作。
```
[root@centos6 test]# git checkout dev
Switched to branch 'dev'
[root@centos6 test]# echo "now doing something ,but a bug need to fix" >>bug.txt 
[root@centos6 test]# git status
# On branch dev
# Changed but not updated:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	modified:   bug.txt
#
no changes added to commit (use "git add" and/or "git commit -a")
[root@centos6 test]# git stash
Saved working directory and index state WIP on dev: 5107bb6   add bug.txt
HEAD is now at 5107bb6   add bug.txt
[root@centos6 test]# git checkout master
Switched to branch 'master'
[root@centos6 test]# git checkout -b bug-102
Switched to a new branch 'bug-102'
[root@centos6 test]# echo " fix bug 102" >> 
bug.txt             .gitignore          解放路世纪东方.txt  
.git/               LICENSE             
[root@centos6 test]# echo " fix bug 102" >> bug.txt 
[root@centos6 test]# git commit -m " fix bug 102" 
# On branch bug-102
# Changed but not updated:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	modified:   bug.txt
#
no changes added to commit (use "git add" and/or "git commit -a")
[root@centos6 test]# git add bug.txt 
[root@centos6 test]# git commit -m " fix bug 102"
[bug-102 3c0a7cc]  fix bug 102
 1 files changed, 1 insertions(+), 0 deletions(-)
[root@centos6 test]# git checkout master
Switched to branch 'master'
[root@centos6 test]# git merge --no-ff -m "meger bug fix 102" bug-102
Merge made by recursive.
 bug.txt |    1 +
 1 files changed, 1 insertions(+), 0 deletions(-)
[root@centos6 test]# git checkout dev
Switched to branch 'dev'
[root@centos6 test]# git stash list
stash@{0}: WIP on dev: 5107bb6 add bug.txt
stash@{1}: WIP on master: 79541ee conflict fixed
[root@centos6 test]# git stash pop
# On branch dev
# Changed but not updated:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	modified:   bug.txt
#
no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (17bf4b7b14eb8140f9b58852b02e01acfcc1c47a)
[root@centos6 test]# ls
bug.txt  LICENSE  解放路世纪东方.txt
[root@centos6 test]# cat bug.txt 
bug test
now doing something ,but a bug need to fix
[root@centos6 test]# git stash list
stash@{0}: WIP on master: 79541ee conflict fixed

```