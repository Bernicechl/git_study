#解决冲突  
1.当master和test分支都commit了相同的文件时,就不能采用快进提交的方式  
2.强行合并的结果如下  
```  
$ git status
# On branch master
# Your branch is ahead of 'origin/master' by 2 commits.
#
# Unmerged paths:
#   (use "git add/rm <file>..." as appropriate to mark resolution)
#
#       both modified:      readme.txt
#
no changes added to commit (use "git add" and/or "git commit -a")
```  

3.查看冲突  
使用`$ vi readme.txt`查看文件内容   
```  
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
<<<<<<< HEAD
Creating a new branch is quick & simple.
=======
Creating a new branch is quick AND simple.
>>>>>>> feature1
``` 
Git用`<<<<<<<`，`=======`，`>>>>>>>`标记出不同分支的内容，修改成：  
`Creating a new branch is quick and simple.`  
后 `git add`并 `git commit`即可   

```  
$ git log --graph --pretty=oneline --abbrev-commit
```可查看分支情况