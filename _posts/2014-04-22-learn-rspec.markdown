---
layout: post
title:  "rspec学习"
date:   2014-04-22 21:37:34
categories: rails
disqus: y
---
rspec:

1.没表单头的测试fill_in 写法：

'''

      before { fill_in 'micropost_content', with: "Lorem ipsum" }
'''
