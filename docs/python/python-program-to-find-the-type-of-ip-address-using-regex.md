# Python 程序使用 Regex

查找 IP 地址的类型

> 原文:[https://www . geeksforgeeks . org/python-program-to-find-type-of-IP-address-use-regex/](https://www.geeksforgeeks.org/python-program-to-find-the-type-of-ip-address-using-regex/)

**先决条件:** [Python Regex](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个 IP 地址作为输入，编写一个 Python 程序来查找 IP 地址的类型，即 **IPv4** 或 **IPv6** 。如果给定的两个都不是，那么打印两个都不是。

### **什么是 IP(互联网协议)地址？**

每台连接到互联网的计算机都由一个唯一的四部分字符串标识，称为其互联网协议(IP)地址。 [**IPv4**](https://www.geeksforgeeks.org/what-is-ipv4/) 和 [**IPv6**](https://www.geeksforgeeks.org/internet-protocol-version-6-ipv6/) 是互联网协议第 4 版和互联网协议第 6 版，IP 第 6 版是互联网协议的新版本，在复杂度和效率上要比 IP 第 4 版好很多。

*   **IPv4** 是 1983 年在阿帕网内投入生产的主要版本。IP 版本四地址是 32 位整数，用十六进制表示。
*   **IPv6** 是互联网工程任务组(IETF)为应对 IP v4 耗尽问题而开发的。IP v6 是 128 位地址，地址空间为 2 <sup>128</sup> ，比 IPv4 大很多。在 IPv6 中，我们使用冒号-Hexa 表示。共有 8 个组，每个组代表 2 个字节。

**示例:**

```py
Input: 192.0.2.126
Output: IPv4

Input: 3001:0da8:75a3:0000:0000:8a2e:0370:7334
Output: IPv6

Input: 36.12.08.20.52
Output: Neither
```

### **进场:**

*   以 IP 地址为输入。
*   现在，使用正则表达式检查这个 IP 地址是否类似于 IPv4 类型的地址。
*   如果是，则打印“IPv4”，否则使用正则表达式检查该 IP 地址是否类似于 IPv6 类型的地址。
*   如果是，则打印“IPv6”。
*   如果地址不像上述任何一种类型，那么我们将打印“都不是”。

**以下是上述方法的实现:**

## 蟒蛇 3

```py
# Python program to find the type of Ip address

# re module provides support
# for regular expressions
import re

# Make a regular expression
# for validating an Ipv4
ipv4 = '''^(25[0-5]|2[0-4][0-9]|[0-1]?[0-9][0-9]?)\.(
            25[0-5]|2[0-4][0-9]|[0-1]?[0-9][0-9]?)\.(
            25[0-5]|2[0-4][0-9]|[0-1]?[0-9][0-9]?)\.(
            25[0-5]|2[0-4][0-9]|[0-1]?[0-9][0-9]?){content}apos;''

# Make a regular expression
# for validating an Ipv6
ipv6 = '''(([0-9a-fA-F]{1,4}:){7,7}[0-9a-fA-F]{1,4}|
        ([0-9a-fA-F]{1,4}:){1,7}:|([0-9a-fA-F]{1,4}:)
        {1,6}:[0-9a-fA-F]{1,4}|([0-9a-fA-F]{1,4}:){1
        ,5}(:[0-9a-fA-F]{1,4}){1,2}|([0-9a-fA-F]{1,4}
        :){1,4}(:[0-9a-fA-F]{1,4}){1,3}|([0-9a-fA-F]{
        1,4}:){1,3}(:[0-9a-fA-F]{1,4}){1,4}|([0-9a-fA
        -F]{1,4}:){1,2}(:[0-9a-fA-F]{1,4}){1,5}|[0-9a
        -fA-F]{1,4}:((:[0-9a-fA-F]{1,4}){1,6})|:((:[0
        -9a-fA-F]{1,4}){1,7}|:)|fe80:(:[0-9a-fA-F]{0,
        4}){0,4}%[0-9a-zA-Z]{1,}|::(ffff(:0{1,4}){0,1}
        :){0,1}((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9
        ])\.){3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0
        -9])|([0-9a-fA-F]{1,4}:){1,4}:((25[0-5]|(2[0-4]
        |1{0,1}[0-9]){0,1}[0-9])\.){3,3}(25[0-5]|(2[0-4]
        |1{0,1}[0-9]){0,1}[0-9]))'''

# Define a function for finding
# the type of Ip address
def find(Ip): 

    # pass the regular expression
    # and the string in search() method
    if re.search(ipv4, Ip):
        print("IPv4")
    elif re.search(ipv6, Ip):
        print("IPv6")
    else:
        print("Neither")

# Driver Code 
if __name__ == '__main__' : 

    # Enter the Ip address
    Ip = "192.0.2.126"

    # calling run function 
    find(Ip)

    Ip = "3001:0da8:75a3:0000:0000:8a2e:0370:7334"
    find(Ip)

    Ip = "36.12.08.20.52"
    find(Ip)
```

**输出:**

```py
IPv4
IPv6
Neither
```