# 面试问题之Linux

<!-- more -->

> 博客内容为[PHP-Interview-QA](https://github.com/colinlet/PHP-Interview-QA)读后笔记

## 目录结构

```sh
/
├── bin #存放二进制可执行文件，常用命令一般都在这里
├── boot #存放用于系统引导时使用的各种文件
├── dev #用于存放设备文件
├── etc #存放系统管理和配置文件
├── home #存放所有用户文件的根目录
├── lib #存放着和系统运行相关的库文件
├── media #linux 系统会自动识别一些设备，当识别后，linux 会把识别的设备挂载到这个目录下
├── mnt #用户临时挂载其他的文件系统
├── opt #额外安装的可选应用程序包所放置的位置
├── proc #虚拟文件系统目录，是系统内存的映射。可直接访问这个目录来获取系统信息
├── root #超级用户的主目录
├── run #是一个临时文件系统，存储系统启动以来的信息
├── sbin #存放二进制可执行文件，只有 root 才能访问
├── srv #该目录存放一些服务启动之后需要提取的数据
├── sys #存放内核相关文件
├── tmp #用于存放各种临时文件，是公用的临时文件存储点
├── usr #用于存放系统应用程序
└── var #用于存放运行时需要改变数据的文件，比如服务的日志文件
```

## Linux命令

* uname -a: 系统信息
* cat /proc/cpuinfo: CPU信息
* env: 环境变量
* free: 查看内存使用量
* df -h: 查看分区使用情况
* du <dir>: 查看具体目录使用情况
* uptime: 查看系统运行时间、用户数、负载
* ifconfig: 查看网络接口的属性
* iptables: 查看防火墙设置
* netstat -lntp: 查看所有监听的端口
* netstat -antp: 查看所有已建立的连接
* ps -ef、ps aux: 查看所有进程
* top: 实时查看进程状况
* w: 查看活动用户
* last: 查看用户登录日志
* crontab: 设置定时任务
* tail -f: 实时查看文件尾部的内容
* awk、cut: 文本处理（[awk、cut命令](https://blog.alan123.xyz/linux/953.html)）

## 查找

* which: 查找命令的位置
* find <obj_dir> -name <file_name>: 查找目标目录下的文件
* locate: 查找文件，但从其自己的数据中查找，速度快

## 标准数据流

* STDIN: 标准输入，0
* STDOUT: 标准输出，1
* STDERR: 标准错误输出，2

## vim

* 向上翻半页: ctrl+u
* 向下翻半页: ctrl+d
* 光标上移: k
* 光标下移: j
* 光标左移: h
* 光标右移: l
* 跳到第一行: gg
* 跳到最后一行: G
* 调到指定行: :n
* 查找: /word
* 查找下一个: n
* 查找上一个: N

## 进程、线程、协程

* 进程: 是一个正在执行的程序，它是系统资源分配的最小单位
* 线程: 相对进程更小，一个进程可能包含多个线程，同一个进程中的线程资源共享，线程是CPU调度的最小单位
* 协程: 比线程还小，协程的调度由程序员操控，没有进程和线程中的上下文切换

## 进程间通信

* 信号量
* 消息队列
* 共享内存
* 信号
* 管道
* 套接字