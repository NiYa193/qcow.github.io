---
title: 本地安装Jekyll及Hexo
date: 2021-02-19 23:00:00
categories: Common
tags: GithubPages
---


# Linux本地安装 Jekyll

## 下载Ruby及依赖
```bash
apt install ruby-full ruby-dev gcc libffi-dev make g++ zlib1g-dev
# 红帽系
yum install ruby ruby-devel libffi-devel
```bash

## 安装Bundler
```bash
sudo gem install bundler
sudo gem install pygments.rb
```

<!-- more -->

## 克隆Github到本地
```bash
git clone git@github.com:NiYa193/qcow.github.io.git && cd qcow.github.io.git
```

## 更新安装bundle
```bash
## 更新时会遇到很多库依赖的问题，直接安装对应库就可以了
bundle update --bundler   ## 可能要输入root密码
## bundle install 遇到的问题，大部分都是缺库，下载对应包就可以了，这提示也是没谁了
bundle install
```
报错提示样例：
```bash
    Gem::Ext::BuildError: ERROR: Failed to build gem native extension.
    
        current directory: /usr/share/gems/gems/commonmarker-0.17.13/ext/commonmarker
    /usr/bin/ruby -r ./siteconf20210221-3115-4zm6ln.rb extconf.rb
    mkmf.rb can't find header files for ruby at /usr/share/include/ruby.h
    
    extconf failed, exit code 1
    
    Gem files will remain installed in /usr/share/gems/gems/commonmarker-0.17.13 for
    inspection.
    Results logged to /usr/lib64/gems/ruby/commonmarker-0.17.13/gem_make.out
    
    An error occurred while installing commonmarker (0.17.13), and Bundler cannot
    continue.
    Make sure that `gem install commonmarker -v '0.17.13' --source 'https://rubygems.org/'`
    succeeds before bundling.
    
    In Gemfile:
      github-pages was resolved to 193, which depends on
        jekyll-commonmark-ghpages was resolved to 0.1.5, which depends on
          jekyll-commonmark was resolved to 1.2.0, which depends on
            commonmarker                                                  
```


## 开启服务
```bash
jekyll serve -H 192.168.1.1 -P 8080  # 虚拟机的话一定是虚拟机的IP
## 如果失败，可以尝试
bundle exec jekyll serve -H 192.168.1.1 -P 8080
```



# windows本地安装 Jekyll

## 下载Ruby
推荐下载 Ruby + Devkit 版本：[链接](https://rubyinstaller.org/downloads/) 

## 安装 Ruby
安装完成后，点击Finish，会跳到cmd命令窗口，选3:
![Finishwindow](https://qcow.github.io/_images/Common/GithubPages/2021-02-19-InstallJekyllAndHexo-1-Finish.png)

检查是否安装完成：
```bash
ruby -v
gem -v
```

## 安装 Jekyll
```bash
gem install jekyll
```

检查是否安装完成：
```bash
jekyll -v
```

## 启动server
```bash
jekyll serve 
```

# 定制化
## 主题选择
主题可以网站选择： [链接](http://jekyllthemes.org)

几个好看的主题：
1. 非常简洁的小猫主题
[CatBook](http://jekyllthemes.org/themes/CATbook/)


# Linux本地安装hexo
## 安装步骤
### 参考网站
[官方网站](https://hexo.io/docs/server.html)
[参考网站-1](https://ezlippi.com/blog/2016/02/jekyll-to-hexo.html)

### 安装软件
mkdir hexo  #创建一个文件夹
cd hexo
npm install -g hexo-cli
npm install hexo --save

### 安装主题
git clone --branch v5.1.2 https://github.com/iissnan/hexo-theme-next themes/next



## 主题推荐：
简洁的next主题[next](https://github.com/iissnan/hexo-theme-next)


## 安装报错
1. 可能原因是国内的源有问题
npm install -g cnpm --registry=https://registry.npm.taobao.org
cnpm install hexo-cli -g
cnpm install hexo --save

