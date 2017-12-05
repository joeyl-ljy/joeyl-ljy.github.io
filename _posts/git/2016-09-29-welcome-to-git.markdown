---
layout: post
title:  "git安装与常见命令"
date:   2016-09-29 16:59:53 +0800
categories: git
tag: [git ssh-key]
---

## GIT的安装与配置

在终端执行后面指令安装，
		
	homebrew /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

完成后，使用以后指令安装Git，
	
	brew install git

安装好Git后，初始化配置，以后每次与Git的交互都会使用该信息。

. 配置用户名：
		
	git config --global user.name "your_name"

. 配置用户邮箱

	git config --global user.email "your_email@gmail.com"

. 指令查看Git的配置信息

	git config --list

. 将远端代码clone到本地目录

	git clone <远端git> <本地目录>

. 提交修改

	git add <文件> // 将有修改的文件添加到本地缓存中 git add . 是添加所有修改
	git commit -m "本次修改信息" // 提交本次修改，一般是在git add之后操作
	git commit --amend // 提交本次修改到上一次的提交
	git reset . // 撤销add
	git rm --cached . // 撤销add

. 切换分支

	git checkout <branch_name>

. 以当前分支为蓝本新建分支并切换到新分支

	git checkout -b <branch_name>

. 当前分支合并其他分支
	
	git rebase <branch_name>

. 回滚到某一个提交版本
	
	git reset --hard/soft <commit_id> // 回滚到某一个版本
	git reset --hard/soft HEAD~<num> // 回滚num个提交

. 提交日志查看方式
	
	git log -p 每一次提交具体差异
	git log —stat 显示文件修改差异，没显示具体修改
	git log —graph 树形状提交记录，可查看分支合并信息
	gitk 查看所有提交记录

. 将其他分支的某次提交应用到该分支
	
	git cherry-pick <commit id>


## 秘钥

. 秘钥生成

Git关联远端仓库时候需要提供公钥，本地保存私钥，每次与远端仓库交互时候，远端仓库会用公钥来验证交互者身份。使用以下指令生成密钥。

	ssh-keygen -t rsa -C "your_email@youremail.com"

生成密钥后，在本地的/Users/当前电脑用户/.ssh目录下会生成两个文件id_rsa、id_rsa.pub，id_rsa文件保存的是私钥，保存于本地，id_rsa.pub文件保存的是公钥，需要将里面内容上传到远端仓库。

. ssh发布失败

项目发布错误：SSHKit::Command::Failed

	ssh-add ~/.ssh/id_rsa









