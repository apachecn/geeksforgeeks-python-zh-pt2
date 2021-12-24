# Python 中使用套接字的简单端口扫描器

> 原文:[https://www . geesforgeks . org/simple-port-scanner-use-sockets-in-python/](https://www.geeksforgeeks.org/simple-port-scanner-using-sockets-in-python/)

**先决条件:**[Python 中的 Socket 编程](http://geeksforgeeks.org/socket-programming-python/)

在开始编程之前，让我们讨论一下端口。在本文中，我们将检查服务器或网站或本地主机的虚拟端口。每个端口都有一个唯一的号码。从 0 开始，主机中有 65，535 个可用端口。我们可以为任何服务分配端口。

**例 1:** 在这个程序中，可以扫描一定范围内的多个端口。

## 蟒蛇 3

```
# Here we import two modules, socket and time

import socket
import time

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# here we asking for the target website
# or host
target = input('What you want to scan?: ')

# next line gives us the ip address
# of the target
target_ip = socket.gethostbyname(target)
print('Starting scan on host:', target_ip)

# function for scanning ports

def port_scan(port):
    try:
        s.connect((target_ip, port))
        return True
    except:
        return False

start = time.time()

# here we are scanning port 0 to 4
for port in range(5):
    if port_scan(port):
        print(f'port {port} is open')
    else:
        print(f'port {port} is closed')

end = time.time()
print(f'Time taken {end-start:.2f} seconds')
```

**输出:**

```
What you want to scan?: localhost
Starting scan on host: 127.0.0.1
port 0 is closed
port 1 is closed
port 2 is closed
port 3 is closed
port 4 is closed
Time taken 8.12 seconds
```

**注意:**您可以在 for 循环中更改范围，以更改要扫描的端口数。扫描一个网站或主机可能需要一定的时间，所以要有耐心。

**示例 2:** 如果您想扫描某个特定端口，请选择此解决方案。

## 蟒蛇 3

```
# importing the sockets module
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
target = input('What you want to scan?: ')

# getting the ip address using gethostbyname
# function
t_IP = socket.gethostbyname(target)
print("Starting scan on host: ", t_IP)

def port_scan(port):
    try:
        s.connect((t_IP, port))
        return True
    except:
        return False

port = int(input("Enter the port number to be scanned: "))

if port_scan(port):
    print('Port', port, 'is open')
else:
    print("port", port, "is closed")
```

**输出:**

```
What you want to scan?: localhost
Starting scan on host:  127.0.0.1
Enter the port number to be scanned: 135
Port 135 is open
```

**注意:**这里我们正在扫描本地主机。你可以扫描任何主机或网站。如果您得到任何错误，那么套接字无法连接到目标，或者您可能在代码中犯了一些错误。

**警告**:未经管理部门许可，扫描服务器或网站的端口，可视为犯罪。有很多免费的网站可以测试，你可以使用它们。