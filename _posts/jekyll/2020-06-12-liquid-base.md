---
layout: post
title: "liquid base"
description: ""
category: "jekyll"
date: 2020-06-12 13:37:32 +0800
tags: []
---
{% include JB/setup %}

{% raw %}
# 对象和变量名 `{{ object }}`

# 标签 `{% %}`
为模板创建逻辑和控制流， 不会产生可见文本。你可以为变量赋值，创建条件语句或者循环条件，但是这些 Liquid 逻辑在生成的页面中是不可见的。
分三类：
## 逻辑控制
if - (elsif/ else)- endif

unless - endunless

case/when - (else) - endcase
## 循环迭代
for [(limit/offset): int]/reversed/ range - (else/ break/ continue) - endfor

cycle

tablerow [(cols/limit/offset): int] range - endtablerow
## 变量赋值
assign, capture - endcapture, increment, decrement
```
{% if %}
content
{% endif %}
=> content
```
# 过滤器
改变 Lquid 对象的输出，可用多个过滤器，用 | 分隔，从左到右应用，类似于 Linux 的管道
{{ posts_collate[loop_index].date | date: "%Y" }}

# 运算符
运算符： ==, !=, >, <, >=, <=, or, and, contains

具有多个and或or运算符的标记中，按从右到左的顺序检查运算符。您不能使用括号来更改操作顺序-括号在Liquid中是无效字符，将阻止标签工作

# Truthy and falsy
在 Liquid 里， 除了 nil 和 falsy 外 其他都是 truthy

# 数据类型
String, Number, Boolean, Nil, Array

# 去除空格
使用连字符 {{-，-}}，{%- 和 -%} 去除 Liquid 输出的左侧或右侧空格

{% endraw %}
