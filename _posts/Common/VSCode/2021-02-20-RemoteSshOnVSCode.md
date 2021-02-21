---
title: VSCdoe连接远程Linux服务器
date: 2021-02-19 23:00:00
categories: Common
tags: VSCode
---

# VSCdoe连接Linux
## 配置步骤
1. 安装插件
VSCode安装Remote-SSH插件

2. 配置
    1. ctrl + p打开配置
    2. 使用 >remote-ssh 搜索打开配置项  
    ![P1](https://github.com/NiYa193/blogimg/raw/master/images/Common/VSCode/2021-02-20-Remote-SSH-P1.png)
    ![P2](https://github.com/NiYa193/blogimg/raw/master/images/Common/VSCode/2021-02-20-Remote-SSH-P2.png)
    ![P3](https://github.com/NiYa193/blogimg/raw/master/images/Common/VSCode/2021-02-20-Remote-SSH-P3.png)
    1. 配置如下：
    ```bash
        Host Ubuntu
        HostName 192.168.253.129
        User Qcow  
    ```

<!-- more -->

## 失败原因
1. 未配置config文件路径
如果连接不上，一般是因为没有配置remote-ssh的配置文件路径引起  
使用ctrl+p打开配置，配置如下：
```bash
C:\Users\Qcow\.ssh\config
```

2. Server未配置TcpForward相关配置
编辑/etc/ssh/sshd_config，打开相应选项，重启sshd服务即可


