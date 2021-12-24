# 使用 IP 地址模块

确定给定 IP 地址是公共还是私有的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-to-确定给定的 ip 地址是公共的还是私有的-使用 ipaddress-module/](https://www.geeksforgeeks.org/python-program-to-determine-if-the-given-ip-address-is-public-or-private-using-ipaddress-module/)

给定一个[有类 IP 地址](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)，任务是找出它是[公共还是私有](https://www.geeksforgeeks.org/difference-between-private-and-public-ip-addresses/)。

**系统的私有 IP 地址**是用于在同一网络内通信的 IP 地址。使用私有 IP，可以在同一网络内发送或接收数据或信息。

**系统的公共 IP 地址**是用于网络外部通信的 IP 地址。公共 IP 地址基本上是由互联网服务提供商分配的。

**示例:**

```
Input : 17.5.7.8
Output : Public

Input : 172.16.0.10
Output : Private

```

为了实现它，我们将使用 Python 3.3 的 ipaddress 模块的 is_private 方法。

```
# importing ip_address from 
# ip address module
from ipaddress import ip_address

def IPAddress(IP: str) -> str:
    return "Private" if (ip_address(IP).is_private) else "Public"

if __name__ == '__main__' : 

    # Public IP
    print(IPAddress('17.5.7.8'))  

    # Private IP
    print(IPAddress('172.16.0.10'))
```

**输出:**

```
Public
Private
```