---
layout: post
title:  "rails-hash(哈希/散列)"
date:   2017-11-29 16:59:53 +0800
categories: ruby
tag: [ruby rails hash]
---

hash(散列/哈希)使用{}，需提供key和value。
rails中，hash通常使用符号作为key，可以交换使用符号和字段串作为key,如：

	self = {
	  :name => "joeyl"
	  :github => "joeyl-ljy"
	}

等价于

	self = {
	  name: "joeyl"
	  github: "joeyl-ljy"	
	}

方法调用上使用hash作为参数时允许省略{}，前提是参数为`方法调用的最后一个参数`

	redirect_to {:action=>"show", :id=>photo.id}

等价于
	
	redirect_to :action=>"show", :id=>photo.id 

等价于

	redirect_to action:"show", id:photo.id

以下同理

	params.require(:search).permit(:search, :page, {name:[]}) 
	
等价于

	params.require(:search).permit(:search, :page, name:[]) 











