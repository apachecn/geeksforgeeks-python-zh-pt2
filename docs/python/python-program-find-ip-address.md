# Python 程序查找 IP 地址

> 原文:[https://www . geesforgeks . org/python-program-find-IP-address/](https://www.geeksforgeeks.org/python-program-find-ip-address/)

IP(互联网协议)地址是分配给连接到 TCP/IP 网络的每台计算机和其他设备(例如，路由器、移动设备等)的标识符，用于定位和识别与网络上其他节点通信的节点。IP 地址通常以人类可读的符号书写和显示，例如 IPv4(32 位 IP 地址)中的 192.168.1.35。
本文重点介绍如何用 python 获取自己电脑的 IP 地址。
首先要导入套接字库，然后使用

```py
IP = socket.gethostbyname(hostname) 
```

然后将 ip 的值打印到 print()函数中，您的 IP 地址作为输出显示在下面给出的程序中。

```py
# Python Program to Get IP Address
import socket   
hostname = socket.gethostname()   
IPAddr = socket.gethostbyname(hostname)   
print("Your Computer Name is:" + hostname)   
print("Your Computer IP Address is:" + IPAddr)   
```

输出:

```py
Your Computer Name is:pppContainer
Your Computer IP Address is:10.98.162.168

```

**相关帖子:** [Java 程序查找你电脑的 IP 地址](https://www.geeksforgeeks.org/java-program-find-ip-address-computer/)

本文由[**aja 0007**](https://auth.geeksforgeeks.org/profile.php?user=ajay0007)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。