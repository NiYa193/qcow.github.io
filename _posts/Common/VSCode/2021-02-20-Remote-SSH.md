---
title: VSCdoe连接远程Linux服务器
date: 2021-02-19 23:00:00
categories: Common
tags: GithubPages
---

# VSCdoe连接Ubuntu

1. 安装插件
VSCode安装Remote-SSH插件

2. 配置
    1. ctrl + p打开配置
    2. >remote-ssh打开配置项
    ![P1](https://qcow.github.io/_posts/Common/VSCode/2021-02-20-Remote-SSH-P1.png)
    ![P2](https://qcow.github.io/_posts/Common/VSCode/2021-02-20-Remote-SSH-P2.png)
    ![P3](https://qcow.github.io/_posts/Common/VSCode/2021-02-20-Remote-SSH-P3.png)
    3. 配置如下：
    ```bash
        Host Ubuntu
        HostName 192.168.253.129
        User fcc  
    ```

3. 失败原因
如果连接不上，一般是因为没有配置remote-ssh的配置文件路径引起  
使用ctrl+p打开配置，配置如下：
```bash
C:\Users\Fcc\.ssh\config
```


