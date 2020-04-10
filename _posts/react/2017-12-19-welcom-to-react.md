---
layout: post
title: "react项目运行"
description: ""
category: "react"
date: 2017-12-19 09:49:51 +0800
tags: []
---
{% include JB/setup %}

# 查看node的版本
	node -v

# 查看npm的版本
	npm -v 

# 查看npm的配置
	npm config list

# 更换npm的registry
	npm config set registry https://registry.npm.taobao.org

# 安装依赖
## package.json
	### npm 安装
	npm install
	npm install --registry 'https://registry.npm.taobao.org'

	### cnpm 安装
	cnpm install
	cnpm install --registry 'https://registry.npm.taobao.org'

## yarn.json
	yarn install




