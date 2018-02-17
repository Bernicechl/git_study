#上传到远程仓库  
##1.生成版本库  
第一次上传要使用`$ git init`生成版本库  
否则会产生如下报错  
`fatal: Not a git repository (or any of the parent directories): .git`  
##2.连接到远程仓库  
```  
$ git remote add origin master  git@github.com:Bernicechl/git_study.git
```
##3.第一次上传文件  
```$ git push -m origin master```  

出现如下错误  
```  
 To github.com:Bernicechl/git_study.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:Bernicechl/git_study.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
 
```  
只要改为`$ git push -f origin master`即可解决问题  
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改  
#从远程仓库克隆代码  
```  
$ git clone git@github.com:Bernicechl/git_study.git
```  
*一般ssh和http均可,但部分可能只支持其中一种*