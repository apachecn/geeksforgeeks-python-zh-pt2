# Python–带插座的简单端口扫描仪

> 原文:[https://www . geesforgeks . org/python-simple-port-scanner-with-sockets/](https://www.geeksforgeeks.org/python-simple-port-scanner-with-sockets/)

可以扫描端口以检查哪些端口接合，哪些端口打开或空闲。在 Python 中，“Socket”模块提供对 BSD 套接字接口的访问，该接口在所有平台上都可用。

**要扫描端口，可以执行以下步骤:**

1]识别主机的 ip 地址
2)创建新的套接字
3)与端口建立连接
3)检查是否收到天气数据
5)关闭连接

要使用套接字模块，我们必须导入它:

```
 import socket 

```

****让我们从 socket 模块中看到更多可以用来创建简单端口扫描器的功能****

创建一个新的套接字对象时使用了 socket()。socket()函数的语法是:

```
 newSocket = socket.socket(socket_family, socket_type) 

```

socket_family 是版本 4 或 6 的 ip 地址。默认情况下，它采用 IPV4。

```
 AF_INET for socket family of address version 4

 AF_INET6 for socket family of address version 6 

```

socket_type 是一种连接类型。默认情况下，它采用 TCP 连接。

```
 SOCK_STREAM  for Socket type of TCP connections 

SOCK_DGRAM for Socket type of UDP connections 

```

返回包含 Python 解释器当前正在执行的机器的主机名的字符串。我们可以使用:

```
 socket.gethostname() 

```

如果主机名在 IPV6 中，则使用以下方法将主机名转换为 IPv4 地址格式。IPv4 地址以字符串形式返回，例如“10.120.30.2”。如果主机名本身是 IPv4 地址，则返回时不会改变。

```
 socket.gethostbyname(hostname) 

```

为了将套接字绑定到地址，我们使用 Bind()方法。套接字必须尚未绑定。地址的格式取决于地址族。该函数的语法如下。

```
 socket.bind(self,address) 

```

要关闭连接，请使用 close()方法。这个方法标记套接字关闭。一旦发生这种情况，对套接字对象的所有后续操作都将失败。远程端将不再接收数据(在排队的数据被刷新之后)。套接字在被垃圾收集时会自动关闭，但建议显式关闭它们，或者在它们周围使用 with 语句。语法是:

```
 socket.close() 

```

让我们看看扫描端口的实际代码。

```
#Python code for simple port scanning

import socket  #importing library 

ip = socket.gethostbyname (socket.gethostname())  #getting ip-address of host

for port in range(65535):      #check for all available ports

    try:

        serv = socket.socket(socket.AF_INET,socket.SOCK_STREAM) # create a new socket

        serv.bind((ip,port)) # bind socket with address

    except:

        print('[OPEN] Port open :',port) #print open port number

    serv.close() #close connection
```