#版本控制-快速上手
- 以git方式进行思考，比较他和Subversion, CVS 版本控制软件的区别，忘记你预想的版本控制软件的控制方式，该以Git方式思考，学习Git。
- 获取和创建项目
	- Git 安装
	- Git clone  下载远程别人项目
	- git init 初始化一个本地化git仓库

#Git基本命令：
- git add ,
- git commit ,
- git reset --hard  ,
- git checkout -,
- git status , 
- git revert, 
- git rm ,
- git mv,
- git diff
区分 下面三个命令区别用法：
git checkout , git reset, git revert命令区别
#分支管理
git branch         查看所有分支以及当前分支（当前分支前面有个星号）

git branch xxx     创建一个xxx分支

git branch -d xxx  删除xxx分支，当前分支不能为xxx分支，比如当前分支为master分支才能删除xxx分支。

git checkout xxx   切换到xxx分支，比如从master分支切换到xxx分支

git merge xxx 将xxx分支的内容合并到当前分支，你要合并那个分支(xxx)内容到另外一个分支（master），必须先切换到master分支，然后通过git merge 命令合并xxx分支内容。
##查看日志
git log 
加参数
git log --oneline

#分享协同
git fetch , git push , git remote，