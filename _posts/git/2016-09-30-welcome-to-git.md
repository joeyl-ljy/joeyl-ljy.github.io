---
layout: post
title:  "git常用命令组合"
date:   2016-09-30 12:59:53 +0800
categories: git
tag: [git ssh-key]
---

克隆项目:git clone 项目路径

1.在主分支拉取最新的代码
	
	git pull 

2.创建新工作分支

	git checkout -b <branch_name>

3.提交修改

	git add <文件> // 将有修改的文件添加到本地缓存中 git add . 是添加所有修改
	git commit -m "本次修改信息" // 提交本次修改，一般是在git add之后操作

4.创建主分支

	git checkout master

5.拉取最新的分支代码

	git pull 

6.切换到之前工作的分支

	git checkout <branch_name>

7.当前分支合并主分支
	
	git rebase master

8.重复4、5步，若有更新，在进行6、7，直到再无最新代码

9.主分支合并工作分支
	
	git rebase <branch_name>

# rebase修改

a.在进行rebase的时候，若出现冲突，则需要解决分支错误,
b.若解决后进行提交修改:
	
	git add .
	git rebase --continue

c.若放弃rebase过程：

	git rebase –-abort
	git rebase –-skip

d.对某个commit重新整理

	git rebase -i commit号

e.对前几个commit重新整理

	git rebase -i HEAD~步数

去到相应的pick，修改为edit，然后esc，并输入:wq进行保存，然后在进行rebase修改。










