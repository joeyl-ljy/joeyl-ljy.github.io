---
layout: post
title: "something should to know"
categories: ruby
date:   2018-06-01 09:12:38 +0800
tags: [ruby]
---
1.
方法：
```
__send__(t, *a) {|*args|
        b.binding.eval("proc{|golf_matchdata| $~ = golf_matchdata }").call($~) if $~
        b.call(*args)
      }
```
2.*a

3.@@golf_hash

4.r = /^#{s.to_s.gsub(/./){"(.*?)" + Regexp.escape($&)}}/

5.1.upto(s.size){|z| s.scan(/./).combination(z)}

6.(?A..?Z)

7.result.pack('c*')

8.gets.chomp() and ARGV

9.render :nothing => true, :status => 200, :content_type => 'text/html' 
to =>
head 200, content_type: "text/html"
