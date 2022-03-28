### 先创建本地库 再推送到 github 远程
git remote add origin https://github.com/THSLQ/JavaScript.git  

* git push -u origin master  
由于远程库是空的，我们第一次推送master分支时，加上了-u参数， 
Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
之后  
从现在起，只要本地作了提交，就可以通过命令：  
* git push origin master  

*PS:	第一次推送远程，需要许可认证*  

如果添加的时候地址写错了，或者就是想删除远程库，可以用git remote rm <name>命令。使用前，建议先用git remote -v查看远程库信息：  
*PS: 此处的“删除”其实是解除了本地和远程的绑定关系，并不是物理上删除了远程库。远程库本身并没有任何改动。要真正删除远程库，需要登录到GitHub，在后台页面找到删除按钮再删除。*

-- 改名字  
git branch -M main  
git push -u origin main  


### Git 分支  
#### I 创建 与 合并分支  
在版本回退里，你已经知道，每次提交，Git都把它们串成一条时间线，这条时间线就是一个分支。