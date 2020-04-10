---
layout: post
title: "posts_collate list time error"
description: ""
category: "jekyll"
date: 2020-06-12 12:34:02 +0800
tags: []
---
{% include JB/setup %}

{% raw %}
# 文章列表下分类排列和时间错乱
查看 _includes/JB/posts_collate 的代码后发现，由两种情况导致：
1.post.previous存在非当前分类的文章

2.年月的判断有误：如若年份不同，月份相同时，月份未显示

```
修改前：
{% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
{% capture next_month %}{{ post.previous.date | date: "%B" }}{% endcapture %}
{% if forloop.last %}
  </ul>
{% else %}
  {% if this_year != next_year %}
    </ul>
    <h2>{{next_year}}</h2>
    <h3>{{next_month}}</h3>
    <ul>
  {% else %}    
    {% if this_month != next_month %}
      </ul>
      <h3>{{next_month}}</h3>
      <ul>
    {% endif %}
  {% endif %}
{% endif %}
```

```
修改后：

{% assign loop_index = forloop.index -1 %}
{% capture next_year %}{{ posts_collate[loop_index].date | date: "%Y" }}{% endcapture %}
{% capture next_month %}{{ posts_collate[loop_index].date | date: "%B" }}{% endcapture %}

{% if forloop.last %}
  </ul>
{% else %}
  {% if this_year != next_year %}
    </ul>
    <h2>{{next_year}}年</h2>
  {% endif %}
  {% if this_year != next_year or this_month != next_month %}
    </ul>
    <h3>{{next_month | date: "%m" }}月</h3>
    <ul>
  {% endif %}
{% endif %}
```
{% endraw %}
