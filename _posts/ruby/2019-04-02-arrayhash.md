---
layout: post
title:  "array to hash array"
date:   2019-04-02 16:13:53 +0800
categories: ruby
tag: [ruby rails]
---

# **识别hash，允许为空
	def a(**c)
	  puts c
	  puts c.to_s
	  puts c.to_json
	  puts c.class
	end

	pry(main)> a
	{}
	{}
	{}
	Hash
	=> nil

	pry(main)> a(a:1)
	{:a=>1}
	{:a=>1}
	{"a":1}
	Hash
	=> nil

	pry(main)> a([1,2])
	ArgumentError: wrong number of arguments (given 1, expected 0)
	from (pry):xxx:in `a'

	pry(main)> a(1)
	ArgumentError: wrong number of arguments (given 1, expected 0)
	from (pry):xxx:in `a'
