---
layout: post
title:  "RVM日常使用"
date:   2014-05-17 19:51:34
categories: rails
disqus: y
---

#RVM使用
##切换ruby版本
* 临时切换
    
    $ rvm use 1.9.3
    
    $ rvm use system
    
    $ ruby -v
    
    ruby 1.8.7 (2009-06-12 patchlevel 174) [universal-darwin10    
* 永久设置
    
    $ rvm use 1.9.3 --default

##切换gemset版本
* 创建某个应用专用的一套gemset
    
    $ rvm gemset create rails222 rails126
    
    $ rvm 1.9.3@rails222
    
    $ rvm 1.9.3@rails126
    
    $ rvm 1.9.3(切换到默认gemset)
