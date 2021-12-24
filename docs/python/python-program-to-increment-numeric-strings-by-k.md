# Python 程序将数字字符串增加 K

> 原文:[https://www . geesforgeks . org/python-program-to-increment-numeric-string-by-k/](https://www.geeksforgeeks.org/python-program-to-increment-numeric-strings-by-k/)

给定字符串列表，编写一个 Python 程序，将数字字符串增加 k

**示例:**

> **输入**:test _ list =[“gfg”、“234”、“is”、“98”、“123”、“best”、“4”]，K = 6
> **输出**:[‘gfg’、‘240’、‘is’、‘104’、‘129’、‘best’、‘10’]
> **解释**:结果中 234、98、4 加 6。
> 
> **输入**:test _ list =[“gfg”、“234”、“is”、“98”、“123”、“best”、“4”]，K = 4
> **输出**:[‘gfg’、‘238’、‘is’、‘102’、‘129’、‘best’、‘8’]
> **解释**:结果中 234、98、4 加 4。

**方法#1:使用**[**str()**](https://www.geeksforgeeks.org/python-str-function/)**+**[**int()**](https://www.geeksforgeeks.org/python-int-function/)**+loop+**[**is digit()**](https://www.geeksforgeeks.org/python-string-isdigit-application/)

在本文中，我们使用 str() + int()执行元素的相互转换任务，并使用 isdigit()检查数字，迭代使用循环完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Increment Numeric Strings by K
# Using str() + int() + loop + isdigit()

# initializing Matrix
test_list = ["gfg", "234", "is", "98", "123", "best", "4"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

res = []
for ele in test_list:

    # incrementing on testing for digit.
    if ele.isdigit():
        res.append(str(int(ele) + K))
    else:
        res.append(ele)

# printing result
print("Incremented Numeric Strings : " + str(res))
```

**输出:**

> 原始列表为:['gfg '，' 234 '，' is '，' 98 '，' 123 '，' best '，' 4']
> 递增数字字符串:['gfg '，' 240 '，' is '，' 104 '，' 129 '，' best '，' 10']

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**is digit()**](https://www.geeksforgeeks.org/python-string-isdigit-application/)

这是执行这项任务的方法之一。与上面类似，使用列表理解来压缩解决方案只有一行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Increment Numeric Strings by K
# Using list comprehension + isdigit()

# initializing Matrix
test_list = ["gfg", "234", "is", "98", "123", "best", "4"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# increment Numeric digits.
res = [str(int(ele) + K) if ele.isdigit() else ele for ele in test_list]

# printing result
print("Incremented Numeric Strings : " + str(res))
```

**输出:**

> 原始列表为:['gfg '，' 234 '，' is '，' 98 '，' 123 '，' best '，' 4']
> 递增数字字符串:['gfg '，' 240 '，' is '，' 104 '，' 129 '，' best '，' 10']