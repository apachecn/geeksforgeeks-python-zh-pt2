# Python–删除重复数字的数字

> 原文:[https://www . geesforgeks . org/python-remove-numbers-with-repeating-digits/](https://www.geeksforgeeks.org/python-remove-numbers-with-repeating-digits/)

给定一个数字列表，任务是编写一个 Python 程序来删除所有有重复数字的数字。

**示例:**

> **输入:** test_list = [4252，6578，3421，6545，6676]
> 
> **输出:** test_list = [6578，3421]
> 
> **说明:** 4252 有 2 次出现 2 因此被移除。所有其他移除的类似情况。
> 
> **输入:** test_list = [4252，6578，3423，6545，6676]
> 
> **输出:** test_list = [6578]
> 
> **说明:** 4252 有 2 次出现 2 因此被移除。所有其他移除的类似情况。

**方法#1:使用** [**设置()**](https://www.geeksforgeeks.org/python-sets/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本例中，我们使用 set()执行消除重复元素的任务，然后将长度与原始长度进行比较。如果找到，返回真，否则返回假。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove numbers with repeating digits
# Using set() + len() + list comprehension

# initializing list
test_list = [4252, 6578, 3421, 6545, 6676]

# printing original list
print("The original list is : " + str(test_list))

# set() used to remove digits
res = [sub for sub in test_list if len(set(str(sub))) == len(str(sub))]

# printing result
print("List after removing repeating digit numbers : " + str(res))
```

**输出:**

```py
The original list is : [4252, 6578, 3421, 6545, 6676]
List after removing repeating digit numbers : [6578, 3421]
```

**方法 2:使用** [**regex()**](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

适当的正则表达式也可以用于检查每个数字重复一次的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove numbers with repeating digits
# Using regex()
import re

# initializing list
test_list = [4252, 6578, 3421, 6545, 6676]

# printing original list
print("The original list is : " + str(test_list))

# regex used to remove elements with repeating digits
regx = re.compile(r"(\d).*\1")
res = [sub for sub in test_list if not regx.search(str(sub))]

# printing result
print("List after removing repeating digit numbers : " + str(res))
```

**输出:**

```py
The original list is : [4252, 6578, 3421, 6545, 6676]
List after removing repeating digit numbers : [6578, 3421]
```