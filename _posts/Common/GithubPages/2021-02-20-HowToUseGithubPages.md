---
title: 如何使用Github Pages
date: 2021-02-20 23:00:19
categories: Common
tags: GithubPages
---

# 如何使用Github Pages
**总体流程如下：**
* 首先Fork或Download一份本项目代码。
* 修改_config.yaml及about.md文件，以变更个人信息。
* 修改_include目录下相关文件，以配置网站统计(analytics.html)，网友评论(comment.html)，右侧栏目(categories.html),热门文章(hot.html),友情链接(links.html)等。
* 修改CNAME文件，以绑定自己的域名。
* 删除_posts下文章，换成你自己的。
* 去谷歌自定义搜索新建一个你的搜索引擎，把你的Id替换根目录下search.html我的ID
* 最后，push到你自己的博客Repo~

<!-- more -->

## Github网站配置
一堆堆，先省略


## 本地Git配置
1. 从Github网站上clone下来
```bash
git clone xxx.io
cd xx.io
```

## 特性说明
### 各文件及文件夹的作用
* CNAME  : 放置自己的域名
* _posts : 文章的存放位置，可以增加子文件夹
* 

### 书写文章

#### 文章的命名
以日期命名才可以被收录，例如
```
2021-02-20-HowToUseGithubPages.md
```

#### 文章的抬头
文章的抬头，可以指定文章的标题、归档、时间、及标签
```css
---
title: 本地安装Jekyll
date: 2021-02-19 23:00:00
categories: Common
tags: GithubPages
---
```

#### 折叠文章
打开这个配置：
```bash
excerpt_separator: <!-- more -->
```
然后在文章中添加
```css
<!-- more -->
```

#### SmallTips
1. 新标签页打开超链接
在引用最后面，添加 {:target="_blank"}，例如：
```
[参考链接](https://blog.csdn.net/sdcxyz/article/details/46803679){:target="_blank"}
```


