---
layout: post
title:  "json 序列化存储 store"
date:   2019-10-12 17:13:53 +0800
categories: ruby
tag: [ruby rails]
---

# json 序列化存储 store
	  store :settings, accessors: [ :color, :name ], coder: JSON
	  serialize :categoriesr

[序列化](https://api.rubyonrails.org/classes/ActiveRecord/Store.html)
