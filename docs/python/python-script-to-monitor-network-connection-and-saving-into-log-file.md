# 监控网络连接并保存到日志文件的 Python 脚本

> 原文:[https://www . geesforgeks . org/python-脚本到监视器-网络-连接-保存到日志文件/](https://www.geeksforgeeks.org/python-script-to-monitor-network-connection-and-saving-into-log-file/)

在本文中，我们将看到如何在 Python 中监控网络连接并保存日志文件。

该脚本的基本思想是提供关于运行脚本的系统是否连接到互联网的实时信息，同时将该信息保存到日志文件中，记录系统何时连接到互联网、何时断开连接以及断开连接的持续时间。

这个脚本是使用 Python 中的[套接字库](https://www.geeksforgeeks.org/socket-programming-python/)制作的，在这个程序中，套接字库用于在网络上发送或接收数据包。

### 日志文件:

只需在当前工作目录中创建一个日志文件来存储互联网连接状态。

## 巨蟒

```py
FILE = os.path.join(os.getcwd(), "networkinfo.log")
```

### ping():

使用此功能，脚本将尝试连接到定义的服务器，以检查系统是否有实时互联网连接。这个任务将使用 python 中的[异常处理](https://www.geeksforgeeks.org/python-exception-handling/) ( [尝试，除了，否则](https://www.geeksforgeeks.org/try-except-else-and-finally-in-python/))来完成。

1.  The system will try to ping a specific server (port on IP)
2.  If the machine connection fails, the EXCEPT statement will be executed.
3.  Otherwise, the connection will be closed after the system successfully connects to the server.

**代号:**

## 蟒蛇

```py
def ping():

    # to ping a particular PORT at an IP
    # if the machine won't receive any packets from
    # the server for more than 3 seconds
    # i.e no connection is
    # made(machine doesn't have a live internet connection)
    # <except> part will be executed
    try:
        socket.setdefaulttimeout(3)

        # AF_INET: address family (IPv4)
        # SOCK_STREAM: type for TCP (PORT)
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

        host = "8.8.8.8"
        port = 53

        server_address = (host, port)

        # send connection request to the defined server
        s.connect(server_address)

    except OSError as error:

        # function returning false after
        # data interruption(no connection)
        return False
    else:

        # the connection is closed after
        # machine being connected
        s.close()
        return True
```

**上述程序中使用的函数**

*   **socket.set defaulttime ():** is a built-in socket library function in python. By setting the default timeout to 3 seconds, we specify that if there is no response from the server for more than 3 seconds, no connection will be established.
*   **socket (socket. AF_INET, socket. Sock _ stream):** socket.socket () is used to define the parameters for connecting two nodes in the network, that is, your system is connected to a specific port on a specific IP so that they can communicate with each other.
    *   AF_INET is an address family, which is used to accept the IP with address type v4 as a parameter, and the defined socket will communicate with it.
    *   SOCK_STREAM is a connection-based protocol. TCP (Transmission Control Protocol) is used in this program to accept a port number as a parameter.

### 计算时间():

不可用时间是指互联网连接不可用的持续时间。使用互联网连接丢失时的停机(停止)时间和互联网连接恢复时的正常运行(开始)时间计算

## Python

T5

```py
def calculate_time(start, stop):

    # to calculate unavailability time
    difference = stop - start
    seconds = float(str(difference.total_seconds()))
    return str(datetime.timedelta(seconds=seconds)).split(".")[0]
```