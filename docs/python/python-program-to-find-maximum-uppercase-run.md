# Python 程序查找最大大写运行

> 原文:[https://www . geesforgeks . org/python-program-to-find-max-大写-run/](https://www.geeksforgeeks.org/python-program-to-find-maximum-uppercase-run/)

给定一个字符串，编写一个 Python 程序来找到大写字符的最大游程。

**示例:**

> **输入**:test _ str = ' geeksforgeeksbest '
> 输出 : 5
> **解释** : ISBES 最好大写。
> 
> **输入**:test _ str = ' geeksforgeiksbest '
> **输出** : 10
> **说明**:geeksfersbes 最好大写。

**方法:使用**[**is upper()**](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)**+循环**

在这种情况下，当遇到非大写字符时，我们会更新最大游程，否则如果字符是大写字符，计数器就会递增。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum uppercase run
# Using isupper() + loop

# initializing string
test_str = 'GeEKSForGEEksIsBESt'

# printing original string
print("The original string is : " + str(test_str))

cnt = 0
res = 0
for idx in range(0, len(test_str)):

    # updating run count on uppercase
    if test_str[idx].isupper():
        cnt += 1

    # on lowercase, update the maxrun
    else :
      if res < cnt :
        res = cnt
        cnt = 0
      else :
        cnt = 0
if test_str[len(test_str) - 1].isupper():
    res = cnt

# printing result
print("Maximum Uppercase Run : " + str(res))
```

**输出:**

```
The original string is : GeEKSForGEEksISBESt
Maximum Uppercase Run : 5
```