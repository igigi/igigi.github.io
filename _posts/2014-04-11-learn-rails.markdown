---
title: model学习
date: 2014-04-11 14:55:34 Z
categories:
- rails
layout: post
disqus: y
---

# Model:

1. 查找对象：

    User.find(1): 根据ID查找某个条目
    
    User.find_by({}): 根据属性查找某个条目（对象）

    User.first 直接查找数据库第一条（返回对象）
    
    User.all 全部（返回数组）

2. 更新对象：

    user.email = "xxxx":更新用户属性（未保存到数据库）
    
    user.save:保存对象到数据库
    
    user.reload.email:基于数据库结构，查询未保存对象信息（内存中）
    
    user.update_attributes({}):一步完成对象的更新，保存到数据库，更新多个熟悉是有原子性

3. 对象属性检查：

    validates :xxx（属性）, presence: true/false, fomat:       { with: regex }, uniqueness: true 验证非空、格式、唯一性。[^1]

[^1]: 高流量时候这样并不能保证唯一性，需要对数据库增加索引，指定唯一性（add_index :users, :email, unique: true）

    user.dup:复制对象，一般用于写测试用例。before_save { self.email = email.downcase }:在Model里增加回调方法，保证存在数据库里的属性是小写或者大写。has_secure_password 配合bcrypt-ruby gem 实现用户登陆验证，密码hash保存在数据库中（自从rainl3 以后）

    user.authenticate("密码"),验证用户

4. 操作对象：

    User.create! 创建对象，如果错误抛出异常，而不是静默的返回false

    Rails 会对model里的有boolean类型的属自动添加“？”方法

    User.find在没找到用户对象的情况下会报异常(ActiveRecord::RecordNotFound)，而User.where则会返回空对象，不会报异常。

    user.any? “对象为空吗？”的意思

**disqus: y**
