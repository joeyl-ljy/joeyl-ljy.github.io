---
layout: post
title:  "array 批处理"
date:   2019-06-15 14:13:53 +0800
categories: ruby
tag: [ruby rails]
---

# 批次处理
	指定数量分批处理
	a = [1,2,3,4]
	a.each_slice(2).to_a
	=> [[1, 2], [3, 4]]
