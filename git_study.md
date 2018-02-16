#关于git

小编在大二时第一次做成熟的项目,当时项目经理要求我们使用git上传代码协作,当时的我还是只小白,git是什么?git是很高端的东西,但是我研究了蛮久还是没搞明白.慢慢的发现其实自己连最基础的概念也没有搞明白,现在从头理一下吧.

#创建版本库

##1.版本库即为仓库(responsibility),这里的文件都能被git管理起来  

``` 
$ mkdir git_study  
$ cd git_study
$ pwd
/d/资料/学习资料/其他/csdn
```

##2.`$ git init` 把这个目录变成git可以管理的仓库
(会增加一个.git文件)

#将文件添加到仓库  

##1.```$ git add gitstudy.txt```  
*执行成功是没有显示任何内容的

## 2.```$ git commit -m "add a txt file"```  
*双引号内部的是注释*

**commit一次可以提交多个文件**

#修改文件内容 

##1.查看状态   
``` 
$ git status  
On branch master  
Changes not staged for commit:  
(use "git add <file>..." to update what will be committed)  
(use "git checkout -- <file>..." to discard changes in working directory)  
 modified:   git_study.txt  
 no changes added to commit (use "git add" and/or "git commit -a")
```

`git status`命令可以让我们时刻掌握仓库当前的状态，上面的命令告诉我们，readme.txt被修改过了，但还没有准备提交的修改。  
  
##2.查看不同
```
$ git diff    #是工作区(work dict)和暂存区(stage)的比较
$ git diff --cached    #是暂存区(stage)和分支(master)的比较
$ git diff HEAD  #查看工作区和版本库里面最新版本的区别
```

#查看历史
##1.`git log`
```  
$ git log
commit 3628164fb26d48395383f8f31179f24e0882e1e0
Author: bernicechl 
Date:   Tue Aug 20 15:11:49 2013 +0800

    append GPL

commit ea34578d5496d7dd233c827ed32a8cd576c5ee85
Author: bernicechl 
Date:   Tue Aug 20 14:53:12 2013 +0800

    add distributed

commit cb926e7ea50ad11b8f9e909c05226233bf755030
Author: bernicechl 
Date:   Mon Aug 19 17:51:55 2013 +0800

    add a txt file 
```  
git log命令显示从最近到最远的提交日志，我们可以看到3次提交，最近的一次是append GPL，上一次是add distributed，最早的一次是add a txt file   
*`$ git log --pretty=oneline`*简化输出,只有id  
##2.回退  
首先，Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交3628164...882e1e0（注意我的提交ID和你的肯定不一样），上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100  
```  
$ git reset --hard HEAD^
HEAD is now at ea34578 add distributed
```
看看git_study.txt的内容是不是版本add distributed：  
```  
$ cat readme.txt  
Git is a distributed version control system.
Git is free software.  
```  
*当想要回退的版本在`git log`中没有显示的时候,在命令行未关闭时可上滑查找id使用  
`$ git reset --hard 3628164`*    

*查看所有操作记录  
`$ git reflog`*