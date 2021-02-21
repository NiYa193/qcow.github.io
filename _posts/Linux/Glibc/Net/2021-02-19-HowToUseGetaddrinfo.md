---
title: Getaddrinfo使用说明
date: 2021-02-19 23:00:00
categories: Linux
tags: Glibc
---

# getaddrinfo使用说明
[参考链接](https://blog.csdn.net/sdcxyz/article/details/46803679)

## Commit
getaddrinfo的作用就是按照提示填充指定的数据结构，以供bind connect 等函数直接使用，无需手动填充所需数据结构 例如 sockaddr，这个函数的作用是替换以前的gethostbyname

<!-- more -->

## Code
示例代码见：
```c
/*
** showipandprot.c 
*/
#include <stdio.h>
#include <string.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>
#include <arpa/inet.h>
#include <netinet/in.h>
 
int main(int argc, char *argv[])
{
    struct addrinfo hints, *res, *p;
    int status;
    char ipstr[INET6_ADDRSTRLEN];
    uint16_t port;
    
    if (argc < 2) {
        fprintf(stderr,"usage: %s hostname  port\n",argv[0]);
        return 1;
    }
    
    memset(&hints, 0, sizeof hints);
    hints.ai_family = AF_UNSPEC; // AF_INET 或 AF_INET6 
    hints.ai_socktype = SOCK_STREAM;
    
    if ((status = getaddrinfo(argv[1], argv[2], &hints, &res)) != 0) {
        fprintf(stderr, "getaddrinfo: %s\n", gai_strerror(status));
        return 2;
    }
    
    printf("IP addresses for %s:\n\n", argv[1]);
    
    for(p = res;p != NULL; p = p->ai_next) {
        void *addr;
        char *ipver;
        
        if (p->ai_family == AF_INET) { // IPv4
            struct sockaddr_in *ipv4 = (struct sockaddr_in *)p->ai_addr;
            addr = &(ipv4->sin_addr);
            ipver = "IPv4";
            port =ntohs(((struct sockaddr_in*)p->ai_addr)->sin_port);
        } else { // IPv6
            struct sockaddr_in6 *ipv6 = (struct sockaddr_in6 *)p->ai_addr;
            addr = &(ipv6->sin6_addr);
            ipver = "IPv6";
            port =ntohs(((struct sockaddr_in6*)p->ai_addr)->sin6_port);
        }
        
        // convert the IP to a string and print it:
        inet_ntop(p->ai_family, addr, ipstr, sizeof ipstr);
        printf(" %s: %s,port is %u\n", ipver, ipstr,port);
    }
    
    freeaddrinfo(res); 
    return 0;
}
```
<br>