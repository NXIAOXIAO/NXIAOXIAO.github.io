---
layout: post
title:  "jekyll本地部署踩坑指南"
date:   2021-04-29 22:00:00 +0800
categories: jekyll update
---
## 1. 安装Ruby
1. 部署jekyll前 需要先部署ruby环境
2. windows 系统需先下载rubyinstaller并安装，勾选默认安装即可 [参考链接](https://rubyinstaller.org/ "rubyinstall下载地址")
3. ruby 安装完成后可以使用 `ruby -v` 查看是否安装完成

## 2.安装jekyll
1. 在ruby正确安装后，可直接使用 `gem install jekyll` 来安装ruby
    - 需确保网络畅通或更换国内源 `gem sources -r https://rubygems.org/ -a https://gems.ruby-china.com/'`
    - 安装完成后可使用 `jekyll -v` 来查看是否安装完成

## 3.部署Blog
1. 安装好jekyll后，可在指定目录下使用 `jekyll new *BlogName*` 来建立Blog目录
2. 然后cd到目录里
3. 使用 `jekyll server` 完成本地部署

## 4.目前自己部署遇到的问题
- ruby 安装好后 jekyll 安装出现问题 ——> 原因是我之前尝试过复数次安装ruby和jekyll，估计存在卸载残留，导致jekyll不能正确安装，后来是使用 `gem update` 然后运行 `gem install jekyll` 解决。（只是自己尝试，未深入研究。）

- `jekyll server` 怎么都运行不了，报错 `cannot load such file -- webrick (LoadError)` 查了一下github issue，说是因为ruby版本太新的缘故，webrick不被默认启用的关系，此时要使用 'bundle add webrick' 来解决。[参考链接](https://github.com/jekyll/jekyll/issues/8523 "github issues")

- 待后续补充