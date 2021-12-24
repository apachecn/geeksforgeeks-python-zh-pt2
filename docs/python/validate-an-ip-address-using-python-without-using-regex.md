# 使用 Python 验证一个 IP 地址，不使用正则表达式

> 原文:[https://www . geesforgeks . org/validate-an-IP-address-使用-python-不使用-regex/](https://www.geeksforgeeks.org/validate-an-ip-address-using-python-without-using-regex/)

给定一个 IP 地址作为输入，任务是编写一个 Python 程序，在不使用正则表达式的情况下检查给定的 IP 地址是否有效。

**什么是 IP(互联网协议)地址？**
每台连接到互联网的计算机都由一个独特的四部分字符串标识，称为其互联网协议(IP)地址。一个 IP 地址(版本 4)由四个数字组成(每个数字介于 0 和 255 之间)，用句点分隔。IP 地址的格式是一个 32 位的数字地址，由四个用句点分隔的十进制数字(称为*八位字节*)组成；每个数字可以写成 0 到 255(例如–0 . 0 . 0 . 0 到 255.255.255.255)。

**示例:**

```py
Input:  192.168.0.1
Output: Valid Ip address

Input: 110.234.52.124
Output: Valid Ip address

Input: 666.1.2.2
Output: Invalid Ip address
```

**方法#1:** 使用 [*计数()*](https://www.geeksforgeeks.org/python-string-count/) 方法检查周期数，然后检查每个周期之间的数字范围。

## 蟒蛇 3

```py
# Python program to verify IP without using RegEx

# explicit function to verify IP
def isValidIP(s):

    # check number of periods
    if s.count('.') != 3:
        return 'Invalid Ip address'

    l = list(map(str, s.split('.')))

    # check range of each number between periods
    for ele in l:
        if int(ele) < 0 or int(ele) > 255 or (i[0]=='0' and len(i)!=1):
            return 'Invalid Ip address'

    return 'Valid Ip address'

# Driver Code
print(isValidIP('666.1.2.2'))
```

**Output**

```py
Invalid Ip address

```

**方法 2:** 使用变量检查周期数，使用 [*设置*](https://www.geeksforgeeks.org/python-sets/) 检查周期之间的数字范围是否在 0 到 255(含)之间。

## 蟒蛇 3

```py
# Python program to verify IP without using RegEx

# explicit function to verify IP
def isValidIP(s):

    # initialize counter
    counter = 0

    # check if period is present
    for i in range(0, len(s)):
        if(s[i] == '.'):
            counter = counter+1
    if(counter != 3):
        return 0

    # check the range of numbers between periods
    st = set()
    for i in range(0, 256):
        st.add(str(i))
    counter = 0
    temp = ""
    for i in range(0, len(s)):
        if(s[i] != '.'):
            temp = temp+s[i]
        else:
            if(temp in st):
                counter = counter+1
            temp = ""
    if(temp in st):
        counter = counter+1

    # verifying all conditions
    if(counter == 4):
        return 'Valid Ip address'
    else:
        return 'Invalid Ip address'

# Driver Code
print(isValidIP('110.234.52.124'))
```

**Output**

```py
Valid Ip address

```