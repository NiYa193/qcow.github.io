---
title: Crash工具使用
date: 2021-02-20 23:00:05
categories: Kernel
tags: Crash
---

# l 命令   
help文档：  
1.用于一个结构的开始地址，结构包含一个指向下一个结构的指针。  
单链表的结构，会以下一个指针的值是如下情况的时候结束：  
（1）空指针  
（2）指向了开始地址  
（3）...  
<!-- more -->

<br>  
<br>

## l 结构体
会把相关的结构体打印出来：  
```C
crash> l sysrq_key_table  
432    };  
433      
434    /* Key Operations table and lock */  
435    DEFINE_SPINLOCK(sysrq_key_table_lock);
436    
437    struct  sysrq_key_op  *sysrq_key_table[36] = {  
438             &sysrq_loglevel_op,             /* 0 */  
439             &sysrq_loglevel_op,             /* 1 */  
440             &sysrq_loglevel_op,             /* 2 */  
441             &sysrq_loglevel_op,             /* 3 */  
```
<br>

# struct命令  
ls
<br>

# dis命令  
反汇编源码  
参考：https://www.cnblogs.com/muahao/p/9925629.html


## dis -sl 
显示出源码上下文  
<br>

## dis -r/r
向前向后查看代码  
<br>

## dis -l
查看代码  
<br>

## dis -x
强制使用16进制  

