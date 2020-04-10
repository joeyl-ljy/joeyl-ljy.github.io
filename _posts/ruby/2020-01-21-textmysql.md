---
layout: post
title:  "rails change column text for mysql"
date:   2020-01-21 19:23:13 +0800
categories: ruby
tag: [ruby rails mysql]
---

The text type handles tinytext, text, mediumtext, and longtext for MySQL

	change_column :articles, :body, :text, :limit => 4294967295

	1 to 255 bytes: TINYTEXT
	256 to 65535 bytes: TEXT
	65536 to 16777215 bytes: MEDIUMTEXT
	16777216 to 4294967295 bytes: LONGTEXT
