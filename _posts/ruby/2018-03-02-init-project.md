---
layout: post
title: "init project"
categories: ruby
date: 2018-03-02 09:27:53 +0800
tags: [ruby rails]
---

1. 项目初始化
  a.新建项目
		rails new new_app_new

  b.初始化master.key和Gemfile等项目隐私配置，设置数据库和基本gem并推送到gitlab
		生成master.key，作为开发的私钥	
		EDITOR="mate --wait" bin/rails credentials:edit
		编辑
		EDITOR="subl --wait" bin/rails credentials:edit
		并在/.gitignore文件增加一行,不做git管理
		/config/master.key
	c.由gitlab管理者项目master在gitlab上确认发布
		git push origin new_app_new

2.增加一些初始化gem，如Capistrano,apipie,rspec,rubocop,httparty等以及其配置
  a.增加Capistrano其配置文件
		# 依赖组建，Cap 项目大量使用组件形式，这样可以让不同需求的人不会引入太多无用功能，根据文档进行组件选取和配置就行
		/Capfile

		# 所有环境的部署配置（通常需设置gitlab代码源的地址，服务器部署位置，以及一些未存储在gitlab的项目配置文件等）
		/config/deploy.rb

		# 不同环境的部署配置文件夹（通常有具体环境的服务主机地址）
		/config/deploy
		/config/environments
		如：
		/config/deploy/staing.rb
		/config/environments/staing.rb
		/config/deploy/production.rb
		/config/environments/production.rb

		#增加环境需增加对应数据库配置

	b.增加GitLab CI/CD
		# 主要服务器权限配置,如DATABASE信息，服务器url
		/.gitlab-ci.yml

		# 根据具体项目定制的一些配置文件
		/ci/*

	c.增加代码规范的配置文件
		/.rubocop.yml

	d.增加rspec配置
		/.rspec

	e.增加brakman配置
	  /config/brakeman.yml

	f.增加active_client相关文件
		/lib/active_client
		/lib/active_client.rb

	g.增加apipie的扩展配置文档
		/config/initializers/apipie.rb
		/app/assets/images
		/app/views/apipie
		/app/views/layouts/apipie
		/vendor
		/lib/apipie

	h.生成线上测试环境配置
		/Dockerfile

	i.修改application.rb增加对应配置
	  # routes
	  # time_zone
	  # i18n
	  # rspec
	  # RackCors配置
	  # apipie依赖库

3.配置推送的项目的gitlab权限
	#设置分支合并规则（选择Fast-forward merge）
	Settings -> General -> Merge request settings
	#本地连接环境服务器的权限，CI/CD配置的各个环节私钥
	Settings -> CI/CD -> Secret variables
	#环境服务器连接代码服务器
	Settings -> Repository -> Deploy Keys

4.推送到服务器
	cap xxx deploy 本地运行或gitlab上操作
	scp 文件到服务器
