---
layout: post
title:  "hash and array to array"
date:   2019-03-02 16:13:53 +0800
categories: ruby
tag: [ruby rails]
---

# *对象转数组,允许参数为空

	def a(*c)
	  puts c
	  puts c.to_s
	  puts c.to_json
	  puts c.class
	end

	pry(main)> a
	[]
	[]
	Array
	=> nil

	pry(main)> a(a:1)
	{:a=>1}
	[{:a=>1}]
	[{"a":1}]
	Array
	=> nil

	pry(main)> a([1,2])
	1
	2
	[[1, 2]]
	[[1,2]]
	Array
	=> nil

	pry(main)> a(1)
	1
	[1]
	[1]
	Array
	=> nil
	