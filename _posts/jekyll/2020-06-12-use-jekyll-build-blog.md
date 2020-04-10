---
layout: post
title: "use jekyll build blog"
description: ""
category: "jekyll"
date: 2020-06-12 10:38:31 +0800
tags: []
---
{% include JB/setup %}

# init blog

## 创建github的博客所在仓库
登陆[Github](https://github.com) 并创建一个名为 USERNAME.github.io 的新存储库 ,参考[GitHubPages](https://pages.github.com/)

```
git clone https://github.com/plusjade/jekyll-bootstrap.git USERNAME.github.io
cd USERNAME.github.io
//配置远程仓库地址
git remote set-url origin git@github.com:USERNAME/USERNAME.github.com.git
```

# Add Gemfile and bundle
```
## Add this lines in Gemfile
source 'https://gems.ruby-china.com'

gem "jekyll", "~> 3.1"
gem "jekyll-sitemap"
gem "pygments.rb"
gem "rake"


## bundle

## 自定义Rakefile

```

# 本地运行jekyll

	jekyll s
	=> Server address: http://127.0.0.1:4000

## 创建目录和主页

以分类作为目录

	rake page name="jekyll" title="About Jekyll"

	=> mkdir -p .
	=> Creating new page: ./jekyll.html

## 创建文章
	
	rake post title="use jekyll build blog" category="jekyll"

	=> mkdir ./_posts/jekyll
	=> Creating new post: ./_posts/jekyll/2020-06-12-use-jekyll-build-blog.md

## 发布
	
	git add .
	git commit -m "Add new content"
	git push origin master


参考： [jekyllbootstrap](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)


