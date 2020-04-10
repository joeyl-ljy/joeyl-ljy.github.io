---
layout: post
title: "raw tags for liquid"
description: ""
category: "jekyll"
date: 2020-06-12 13:24:28 +0800
tags: []
---
{% include JB/setup %}
{% raw %}

在 Jekyll里， `{% %}` 会被识别Liquid 的tags, 若想显示，需要在外层套上一层raw标签`{% raw %} content {% Endraw %}`
```
{% raw %}
{% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
//endraw 小写
{% Endraw %}
```
{% endraw %}
