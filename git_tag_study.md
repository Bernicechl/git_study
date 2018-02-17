#tag
1.切换到需要打标签的分支上(  

默认标签是打在最新提交的commit上的,要给过去的打标签,方法是找到历史提交的commit ,  

`$ git log --pretty=oneline --abbrev-commitid`，然后打上就可以了)  

2.命令git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id；

3.git tag -a <tagname> -m "blablabla..."可以指定标签信息；

4.git tag -s <tagname> -m "blablabla..."可以用PGP签名标签；

5.命令git tag可以查看所有标签。  
  

#tag operation  

1.命令git push origin <tagname>可以推送一个本地标签；

2.命令git push origin --tags可以推送全部未推送过的本地标签；

3.命令git tag -d <tagname>可以删除一个本地标签；

4.命令git push origin :refs/tags/<tagname>可以删除一个远程标签。