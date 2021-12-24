# Python–根据字符串的数字部分对给定的字符串列表进行排序

> 原文:[https://www . geesforgeks . org/python-按字符串的数字部分排序给定字符串列表/](https://www.geeksforgeeks.org/python-sort-given-list-of-strings-by-part-the-numeric-part-of-string/)

给定一个字符串列表。任务是根据字符串的数字部分对列表进行排序。

**示例:**

> **输入**:test _ list =[“Gg34”、“is67”、“be3st”、“f23or”、“ge9eks”]
> **输出**:[‘be3st’、‘ge9eks’、‘f23or’、‘Gg34’、‘is67’]
> **解释** : 3 < 9 < 23 < 34 < 67、从字符串中提取的数字。
> 
> **输入**:test _ list =[“GfG4”、“is67”、“be3st”、“f23or”、“ge9eks”]
> **输出**:[‘be3st’、‘GfG4’、‘ge9eks’、‘f23or’、‘is67’]
> **解释** : 3 < 4 < 9 < 23 < 67、从字符串中提取的数字。

**方法#1:使用 sort() + re.findall()**

在本例中，我们使用 [sort()](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) 执行排序任务，显式函数用于使用 findall()提取数字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Strings on numerical substrings
# Using sort() + findall()
import re

# helper function to perform sort
def num_sort(test_string):
    return list(map(int, re.findall(r'\d+', test_string)))[0]

# initializing list
test_list = ["Gfg34", "is67", "be3st", "f23or", "ge9eks"]

# printing original list
print("The original list is : " + str(test_list))

# calling function
test_list.sort(key=num_sort)

# printing result
print("Strings after numerical Sort  : " + str(test_list))
```

**输出:**

> 原始列表为:[' Gg34 '，' is67 '，' be3st '，' f23or '，' ge9eks']
> 数字排序后的字符串:['be3st '，' ge9eks '，' f23or '，' Gg34 '，' is67']

**方法 2:使用 sort()+**[**【λ】**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+findall()**

在这种情况下，我们执行类似的功能，但不同的是，我们使用 lambda 函数而不是外部函数来执行排序任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Strings on numerical substrings
# Using sort() + lambda + findall()
import re

# initializing list
test_list = ["Gfg34", "is67", "be3st", "f23or", "ge9eks"]

# printing original list
print("The original list is : " + str(test_list))

# findall() getting all integers.
# conversion to integers using map()
test_list.sort(key=lambda test_string : list(
    map(int, re.findall(r'\d+', test_string)))[0])

# printing result
print("Strings after numerical Sort  : " + str(test_list))
```

**输出:**

> 原始列表为:[' Gg34 '，' is67 '，' be3st '，' f23or '，' ge9eks']
> 数字排序后的字符串:['be3st '，' ge9eks '，' f23or '，' Gg34 '，' is67']