# 从客户端发送和接收消息的 Python 程序

> 原文:[https://www . geesforgeks . org/python-发送和接收客户端消息的程序/](https://www.geeksforgeeks.org/python-program-that-sends-and-recieves-message-from-client/)

套接字编程是连接网络上两个节点相互通信的一种方式。一个套接字(节点)监听某个 IP 的特定端口，而另一个套接字则与另一个套接字建立连接。服务器形成侦听器套接字，而客户端则连接到服务器。
socket 编程是通过导入 Socket 库，制作一个简单的 Socket 开始的。

```py
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

这里我们创建了一个套接字实例，并向它传递了两个参数。第一个参数是 **AF_INET** ，第二个参数是 **SOCK_STREAM** 。 **AF_INET** 指地址族 ipv4。SOCK_STREAM 表示面向连接的 TCP 协议。
**注:**更多信息请参考 Python 中的[Socket Programming](https://www.geeksforgeeks.org/socket-programming-python/)
**现在我们可以使用 server 连接到服务器了:**
Server 是一个为网络或互联网上的其他计算机提供服务的程序。类似地，客户机是从服务器接收服务的程序。当服务器想要与客户端通信时，就需要一个套接字。套接字是服务器和客户端之间的连接点。
**向客户端发送消息的 TCP/IP 服务器程序。**

## 蟒蛇 3

```py
import socket

# take the server name and port name
host = 'local host'
port = 5000

# create a socket at server side
# using TCP / IP protocol
s = socket.socket(socket.AF_INET,
                  socket.SOCK_STREAM)

# bind the socket with server
# and port number
s.bind(('', port))

# allow maximum 1 connection to
# the socket
s.listen(1)

# wait till a client accept
# connection
c, addr = s.accept()

# display client address
print("CONNECTION FROM:", str(addr))

# send message to the client after
# encoding into binary string
c.send(b"HELLO, How are you ? \
       Welcome to Akash hacking World")

msg = "Bye.............."
c.send(msg.encode())

# disconnect the server
c.close()
```