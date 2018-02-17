#创建与合并分支  
##1.创建并切换到dev分支  
```  
$ git checkout -b dev
```
这一步相当于
```  
$ git branch dev  
$ git checkout dev
```  
##2.`$ git branch`查看当前分支,当前分支前面会有一个`*`
##3.对当前分支操作(和master操作是一样的,不影响master)  
##4.切换回master分支  
```  
$ git merge dev
Updating d17efd8..fec145a
Fast-forward
 readme.txt |    1 +
 1 file changed, 1 insertion(+)
```  
`Fast-forward`Git告诉我们，这次合并是“快进模式”，也就是直接把master指向dev的当前提交，所以合并速度非常快。

当然，也不是每次合并都能Fast-forward,后期学到了我再补充  

*  补充: `$ git merge --no-ff -m "merge with no-ff" dev`  
(1)请注意--no-ff参数，表示禁用Fast forward  
(2) 因为本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去。*
##5.`$ git merge dev`把dev的内容合并到master上  
##6.`$ git branch -d dev`删除dev分支  
##7.`$ git branch`查看当前分支,只剩下master分支了  

#小结  
查看分支 `$ git branch` 
创建分支 `$ git branch <name>`  
切换分支 `$ git checkout <name>`  
创建+切换分支 `$ git checkout <name> `  
合并某分支到当前分支 `$ git merge <name>`  
删除分支 `$ git branch -d <name>` 

