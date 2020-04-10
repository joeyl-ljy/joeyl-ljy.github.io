---
layout: post
title:  "rbenv and homebrew"
date:   2018-10-08 12:59:53 +0800
categories: ruby
tag: [ruby rails]
---

rbenv 与 homebrew

1. 安装Homebrew终端指令    官网：http://brew.sh/index_zh-cn.html （安装完退出终端）

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

2. 然后利用homebrew安装和更新rbenv
	安装
	brew install rbenv
	更新最新的rebenv及更新ruby-build最新发布的Ruby版本
	brew upgrade rbenv ruby-build

3.然后选择要安装的ruby版本  （rbenv就是用来管理多个版本的ruby使用的）

rbenv install --list	# 列出所有 ruby 版本rbenv install 2.2.2	# 安装 2.2.2版本的ruby 


列出版本


rbenv versions	# 列出安装过的版本rbenv version	# 列出正在使用的版本


设置要使用的ruby版本


rbenv global 2.2.2	# 设置全局默认使用的版本rbenv shell 2.2.2	# 切换ruby版本

卸载ruby版本

rbenv uninstall 2.2.2	# 删除2.2.2版本的ruby
