## Feature分支
feautre 其实和bug分支是一样的，创建分支，然后合并到dev,或者master上。

这个测试是，新功能开发，中途接到通知，放弃开发的解放方法。

```
[root@centos6 test]# cd test/
[root@centos6 test]# ls
bug.txt  LICENSE  解放路世纪东方.txt
[root@centos6 test]# git checkout -b feature-vulcan
M	bug.txt
Switched to a new branch 'feature-vulcan'
[root@centos6 test]# echo "vulcan" >> vulcan.py
[root@centos6 test]# git add vulcan.py 
[root@centos6 test]# git commit -m "add feautre function vulcan"
[feature-vulcan dbb4a15] add feautre function vulcan
 1 files changed, 1 insertions(+), 0 deletions(-)
 create mode 100644 vulcan.py
[root@centos6 test]# git checkout dev
M	bug.txt
Switched to branch 'dev'
[root@centos6 test]# git branch -d feature-vulcan
error: The branch 'feature-vulcan' is not fully merged.
If you are sure you want to delete it, run 'git branch -D feature-vulcan'.
[root@centos6 test]# git branch -D feature-vulcan
Deleted branch feature-vulcan (was dbb4a15).

```