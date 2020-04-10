---
layout: post
title:  "rails项目创建与运行"
date:   2016-10-30 12:59:53 +0800
categories: ruby
tag: [ruby rails]
---

初始化项目，创建项目目录
		
	rails new 项目名

在运行到bundle时候， command+c 退出。

修改项目根目录的 Gemfile 文件中 source的值 改为：
		
	'https://gems.ruby-china.org'

再运行

	bundle install


  rails server 运行项目 (rails s)

默认端口：3000，也可以使用 rails s -p 端口号 使用其他端口

此时，控制台显示如下，就是项目运行成功：

	=> Booting Puma
	=> Rails 5.1.3 application starting in development on http://localhost:3000
	=> Run `rails server -h` for more startup options
	Puma starting in single mode...
	* Version 3.10.0 (ruby 2.3.1-p112), codename: Russell's Teapot
	* Min threads: 5, max threads: 5
	* Environment: development
	* Listening on tcp://0.0.0.0:3000
	Use Ctrl-C to stop
