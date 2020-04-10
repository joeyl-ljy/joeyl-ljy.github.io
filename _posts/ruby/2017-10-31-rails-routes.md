---
layout: post
title:  "rails数据库与路由"
date:   2017-10-31 13:59:53 +0800
categories: ruby
tag: [ruby rails]
---

# 数据库初始化

1.运行重建数据库（5.0/4.2）

	rails db:create db:migrate db:seed
	rails db:drop db:create db:migrate db:seed
	bundle exec rake db:drop db:create db:migrate db:seed 

2.若使用gem：seed_fu
	
	rails db:seed_fu

3.若使用gem：china_region_fu
	
	rails china_region_fu:import

# 路由

路由所在目录是：config/routes.rb

1.查看路由
	
	rails routes

2.Rails 资源路由有两种，resources 和 resource

	resources :photos
	resource  :photo

分别生成七个路由地址和六个路由地址。

# 对动作进行限制

	resources :photos, :only => [:index, :show]
	resources :photos, :except => :destroy

# 添加额外的动作

	1.成员路由

	resources :photos do
	  member do
	    get 'preview'
	  end
	end

	resources :photos do
	  get 'preview', :on => :member
	end

	2.集合路由

	resources :photos do
	  collection do
	    get 'search'
	  end
	end

	resources :photos do
	  get 'search', :on => :collection
	end

	3.指定控制器

	resources :photos, :controller => "images"

	4.指定格式限制

	resources :photos, :constraints => {:id => /[A-Z][A-Z][0-9]+/}
	
	constraints(:id => /[A-Z][A-Z][0-9]+/) do
	  resources :photos
	  resources :accounts
	end

	5.改变 Helper

	resources :photos, :as => "images"

	6.改变匹配路径动的动作

	resources :photos, :path_names => { :new => 'make', :edit => 'change' }

	scope :path_names => { :new => "make" } do
	  resources :photos
	  resources :accounts
	end

	7.改变匹配的路径的资源名

	resources :categories, :path => "kategorien"
	resources :posts, :path => "/admin/posts"

	scope :path => "/admin" do
	  resources :posts, :comments
	end

	scope "/admin" do
	  resources :posts, :comments
	end

	8.控制器模块

	resources :posts, :module => "admin"

	scope :module => "admin" do
	  resources :posts, :comments
	end

	9.控制器命名空间

	namespace :admin do
	  resources :photos, :comments
	end

	10.嵌套路由

	resources :magazines do
	  resources :ads
	end
	
	11.根目录

	root 'pages#main'

	12.路径path和url
	所有路由对应的路径都有对应的 _path 形式和 _url 形式
	前者的返回值是路径，后者的返回值是路径加上由当前的主机名、端口和路径前缀组成的前缀。
	从一个域重定向到另一个域，需要完整的URL,如：
	photo_url(domain:"xxx.com",port:"8080",photo:photo)
	其他情况可直接使用：photo_path(photo)
