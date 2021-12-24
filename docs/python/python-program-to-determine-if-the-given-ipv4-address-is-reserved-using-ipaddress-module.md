# 使用 IP 地址模块

确定给定 IPv4 地址是否被保留的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-确定给定 ipv4 地址是否被保留-使用-ipaddress-module/](https://www.geeksforgeeks.org/python-program-to-determine-if-the-given-ipv4-address-is-reserved-using-ipaddress-module/)

给定一个 [IPv4 地址](https://www.geeksforgeeks.org/what-is-ipv4/)，任务是确定是否预留(即属于[E 类](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/))。

**什么是 E 级？**

属于 E 类的 IP 地址被保留用于实验和研究目的。E 类的 IP 地址范围为 240 . 0 . 0 . 0–255 . 255 . 255 . 254。这个类没有任何子网掩码。E 类第一个二进制八位数的高位总是设置为 1111。

**示例:**

```py
Input : 10.0.0.1
Output : Not Reserved

Input : 241.0.0.133
Output : Reserved

```

为了实现它，我们将使用 Python3.3 的 **ipaddress** 模块的 **is_reserved** 方法

```py
# importing ip_address
# from ipaddress module
from ipaddress import ip_address

def reservedIPAddress(IP: str) -> str:
    return "Reserved" if (ip_address(IP).is_reserved) else "Not Reserved"

if __name__ == '__main__' : 

    # Not Reserved
    print(reservedIPAddress('10.0.0.1')) 

    # Reserved
    print(reservedIPAddress('241.0.0.133')) 
```

**输出:**

```py
Not Reserved
Reserved

```