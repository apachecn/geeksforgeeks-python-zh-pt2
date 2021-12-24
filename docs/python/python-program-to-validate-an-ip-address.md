# 验证 IP 地址的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-validate-an-IP-address/](https://www.geeksforgeeks.org/python-program-to-validate-an-ip-address/)

**先决条件:** [Python Regex](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个 IP 地址作为输入，编写一个 Python 程序来检查给定的 IP 地址是否有效。

**什么是 IP(互联网协议)地址？**
每台连接到互联网的计算机都由一个独特的四部分字符串标识，称为其互联网协议(IP)地址。一个 IP 地址(版本 4)由四个数字组成(每个数字介于 0 和 255 之间)，用句点分隔。IP 地址的格式是一个 32 位的数字地址，由四个用句点分隔的十进制数字(称为*八位字节*)组成；每个数字可以写成 0 到 255(例如–0 . 0 . 0 . 0 到 255.255.255.255)。

**示例:**

```
Input:  192.168.0.1
Output: Valid Ip address

Input: 110.234.52.124
Output: Valid Ip address

Input: 666.1.2.2
Output: Invalid Ip address 

Input:25.99.208.255 
Output: Valid Ip address
```

在这个程序中，我们使用 [**搜索()**](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/) 方法的 *re 模块*。
**re.search() :** 这个方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。

让我们看看验证 IP 地址的 Python 程序:

## 蟒蛇 3

```
# Python program to validate an Ip address

# re module provides support
# for regular expressions
import re

# Make a regular expression
# for validating an Ip-address
regex = "^((25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9])\.){3}(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9]){content}quot;

# Define a function for
# validate an Ip address
def check(Ip):

    # pass the regular expression
    # and the string in search() method
    if(re.search(regex, Ip)):
        print("Valid Ip address")

    else:
        print("Invalid Ip address")

# Driver Code
if __name__ == '__main__' :

    # Enter the Ip address
    Ip = "192.168.0.1"

    # calling run function
    check(Ip)

    Ip = "110.234.52.124"
    check(Ip)

    Ip = "366.1.2.2"
    check(Ip)
```

**Output:** 

```
Valid Ip address
Valid Ip address
Invalid Ip address
```