# 在 Python 中处理 IP 地址

> 原文:[https://www . geesforgeks . org/使用 python 中的 ip 地址/](https://www.geeksforgeeks.org/working-with-ip-addresses-in-python/)

**IP(互联网协议)**-地址是计算机网络的基本概念，它为网络提供地址分配能力。Python 提供了*IP 地址*模块，用于根据 IP 地址的类型 *(IPv4 或 IPv6)* 对其进行验证和分类。该模块还用于执行各种操作，如算术、比较等，以操作 IP 地址。

### **验证 IP 地址-**

为了验证 ip 地址，python 使用了由*IP 地址*模块提供的 *ip_address()* 功能，如果 IP 的值超出了 IP 地址类型的范围，则会引发错误。

*   **IPv4:** It is a 32-bit number, usually written in decimal digits, with the format of four 8-bit numbers separated by dots, which is used to identify the network interface of the machine. If the range value exceeds 0 to 255, the *IP _ address ()* function will throw an error.

## 蟒 3

```
# Import module
import ipaddress

# Example of valid IPv4 address
print (ipaddress.ip_address(u'175.198.42.211'))

# Invalid IPv4 address raises error
print (ipaddress.ip_address(u'175.198.42.270'))
```