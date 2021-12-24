# Python 程序检查给定的字符串是 IPv4 还是 IPv6 或者无效

> 原文:[https://www . geesforgeks . org/python-program-to-check-如果给定的字符串是-IP v4-或-IPv6-或-无效/](https://www.geeksforgeeks.org/python-program-to-check-if-the-given-string-is-ipv4-or-ipv6-or-invalid/)

给定一个字符串。任务是检查给定的字符串是 [IPv4](https://www.geeksforgeeks.org/what-is-ipv4/) 还是 [IPv6](https://www.geeksforgeeks.org/what-is-ipv6/) 或者无效。

**示例:**

> **输入:**“192 . 168 . 0 . 1”
> **输出:** IPv4
> **说明:**是有效的 IPv4 地址
> 
> **输入:**“2001:0db 8:85 a3:0000:0000:8a2e:0370:7334”
> **输出:** IPv6
> **说明:**是有效的 IPv6 地址
> 
> **输入:**“255 . 32 . 555 . 5”
> **输出:**无效
> **说明:**是无效的 IPv4 地址，因为第三个八位字节值(即 555)大于 255。
> 
> **输入:**“250.32:555.5”
> **输出:**无效
> **解释:**给定字符串无效，因为它由:和组成。

为了实现上述问题，我们将使用 Python 中的`ipaddress`模块。本模块提供创建、操作和操作 IPv4 和 IPv6 地址和网络的功能。

下面是实现。

```
from ipaddress import ip_address, IPv4Address

def validIPAddress(IP: str) -> str:
    try:
        return "IPv4" if type(ip_address(IP)) is IPv4Address else "IPv6"
    except ValueError:
        return "Invalid"

if __name__ == '__main__' :  

    # Enter the Ip address 
    Ip = "192.168.0.1"
    print(validIPAddress(Ip)) 

    Ip = "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
    print(validIPAddress(Ip)) 

    Ip = "256.32.555.5"
    print(validIPAddress(Ip))  

    Ip = "250.32:555.5"
    print(validIPAddress(Ip))
```

**输出:**

```
IPv4
IPv6
Invalid
Invalid
```