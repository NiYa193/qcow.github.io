---
title: Github Pages中如何使用图片
date: 2021-02-23 23:09:00
categories: Common
tags: GithubPages
---

# Github Pages中如何使用图片
想着给Github Pages添加个图片，但又不想使用其他工具作图床，所以想着看能否用博客的仓库一并作图床。
这里为真心困扰了好久，网上案例都抄的太过分，没有一个能解决的。

## 同仓库方案
1. 在Github-Pages仓库里面创建一个文件夹。
比如我的，与_posts并列，叫_images

2. 将图片上传到仓库，就是正常Git push流程，不会的在网上搜下就可以。

3. 在Github网页点开这个文件，可以获得类似的链接：
```
https://github.com/user/blogimg/blob/master/images/test.png
```

4. 将链接中的blob换成raw，就可以当作Markdown的链接来使用了。
>这里真心困扰了我很久。。。

<br>

## 单独仓库方案
当然，如果想分开管理图片和文章，也可以单独使用一个仓库做图片仓库，看个人喜好。
我觉得放在一起比较好管理。
方法同上，只是多了一个创建新仓库的流程，也是网上查吧，指导非常详细。

<br>

![Dog](https://github.com/NiYa193/qcow.github.io/raw/gh-pages/_images/Common/GithubPages/2021-02-23-HowToUsePictureOnGithubPages-Dog.png)

