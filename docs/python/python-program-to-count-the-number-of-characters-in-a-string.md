# Python 程序计算字符串中的字符数

> 原文:[https://www . geesforgeks . org/python-程序-计算字符串中的字符数/](https://www.geeksforgeeks.org/python-program-to-count-the-number-of-characters-in-a-string/)

给定一个字符串。任务是返回字符串中的字符数。

**示例:**

> **输入** : test_str = 'geeksforgeeks！！$***最好 4 所有极客 10-0'
> **输出** : 25
> **解释**:只有字母，计算时是 25
> 
> **输入** : test_str = 'geeksforgeeks！！$***最适合所有极客 10-0 '
> **输出** : 27
> **解释**:只有字母，计数后是 27

**方法#1:使用 isalpha() + len()**

在这种方法中，我们使用 [isalpha()](https://www.geeksforgeeks.org/python-string-isalpha-application/) 来检查每个字符是否是字母表，并且使用 [len()](https://www.geeksforgeeks.org/python-string-length-len/) 来获得字母表列表的长度以获得计数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Alphabets Frequency in String
# Using isalpha() + len()

# initializing string
test_str = 'geeksforgeeks !!$ is best 4 all Geeks 10-0'

# printing original string
print("The original string is : " + str(test_str))

# isalpha() to computation of Alphabets
res = len([ele for ele in test_str if ele.isalpha()])

# printing result
print("Count of Alphabets : " + str(res))
```

**Output**

> 原来的字符串是:geeksforgeeks！！$最好是 4 所有极客 10-0
> 字母计数:27

**方法 2:使用 ascii _ 大写()+ascii _ 小写()+ len()**

在本例中，我们使用内置函数来执行获取大写和小写字母组合的任务，len()返回 frequency。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Alphabets Frequency in String
# Using ascii_uppercase() + ascii_lowercase() + len()
import string

# initializing string
test_str = 'geeksforgeeks !!$ is best 4 all Geeks 10-0'

# printing original string
print("The original string is : " + str(test_str))

# ascii_lowercase and ascii_uppercase
# to check for Alphabets
res = len([ele for ele in test_str if ele in string.ascii_uppercase or ele in string.ascii_lowercase])

# printing result
print("Count of Alphabets : " + str(res))
```

**Output**

> 原来的字符串是:geeksforgeeks！！$最好是 4 所有极客 10-0
> 字母计数:27