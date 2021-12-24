# Python 程序查找两个 IP 地址属于同一网络还是不同网络

> 原文:[https://www . geesforgeks . org/python-程序查找如果两个 ip 地址属于相同或不同的网络/](https://www.geeksforgeeks.org/python-program-to-find-if-two-ip-address-belongs-to-same-or-different-network/)

**先决条件:** [无类域间路由(CIDR)](https://www.geeksforgeeks.org/classless-inter-domain-routing-cidr/)

在 [CIDR 符号](https://www.geeksforgeeks.org/classless-inter-domain-routing-cidr/)中给定两个 IP 地址，确定它们属于同一个网络还是不同的网络。如果两个 IP 地址的[网络标识](https://practice.geeksforgeeks.org/problems/what-is-network-id-and-host-id)相同，则称两个 IP 地址在同一个网络中。

**示例:**

> **输入:** IP1 = 192.168.1.0/8，IP2 = 192.32.45.7/8
> **输出:**同一个网络
> **说明:**两个 IP 地址的网络 ID 的位数是 8 位，两个 IP 地址的前
> 8 位(即第 1 个八位字节)是相同的(即 192)。因此两个 IP 地址
> 属于同一个网络。
> 
> **输入:** IP1 = 17.53.128.0/20，IP2 = 17.53.127.0/20
> **输出:**不同网络
> **说明:**两个 IP 地址的网络 ID 位数都是 20 位，但两个 IP 地址的前
> 20 位是不同的。因此，两个 IP 地址属于不同的
> 网络。

为了实现它，我们将使用 Python 3.3 的 ipaddress 模块的 **ip_network** 和 **network_address** 方法。

```
# importing ip_network from ipaddress module
from ipaddress import ip_network

def sameNetwork(IP1: str, IP2: str) -> str:

    a = ip_network(IP1, strict = False).network_address
    b = ip_network(IP2, strict = False).network_address

    if(a == b) :
        return "Same Network" 

    else :
        return "Different Network"

# main function    
if __name__ == '__main__' : 

    # Same Network  
    print(sameNetwork('192.168.1.0/8', '192.32.45.7/8'))  

    # Different Network  
    print(sameNetwork('17.53.128.0/20', '17.53.127.0/20'))

```

**输出:**

```
Same Network
Different Network
```