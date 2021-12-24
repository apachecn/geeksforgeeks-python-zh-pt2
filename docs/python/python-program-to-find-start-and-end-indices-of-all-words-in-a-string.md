# Python 程序，用于查找字符串中所有单词的开始和结束索引

> 原文:[https://www . geesforgeks . org/python-program-to-find-start-end-indexs-of-all-in-words-in-string/](https://www.geeksforgeeks.org/python-program-to-find-start-and-end-indices-of-all-words-in-a-string/)

给定一个字符串，返回每个单词的所有开始索引和结束索引。

**示例:**

> **输入**:test _ str = ' geekforgeks is Best '
> **输出** : [(1，12)，(16，17)，(19，22)]
> **解释**:“Best”从第 19 个索引开始，到第 22 个索引结束。
> 
> **输入**:test _ str = ' geekforgeks is Best '
> **输出** : [(1，12)，(17，18)，(20，23)]
> **解释**:“Best”从第 20 个索引开始，到第 23 个索引结束。

**方法:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**regex**](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)**+finditer()**

在这种情况下，我们使用 finditer()和 regex 提取所有单词，为了获得初始和结束索引，我们使用 start()和 end()并使用列表理解以元组列表的形式封装。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Word Ranges in String
# Using list comprehension + regex + finditer()
import re

# initializing string
test_str = ' Geekforgeeks   is Best    for  geeks'

# printing original string
print("The original string is : " + str(test_str))

# regex to get words, loop to get each start and end index
res = [(ele.start(), ele.end() - 1) for ele in re.finditer(r'\S+', test_str)]

# printing result
print("Word Ranges are : " + str(res))
```

**Output**

```
The original string is :  Geekforgeeks   is Best    for  geeks
Word Ranges are : [(1, 12), (16, 17), (19, 22), (27, 29), (32, 36)]

```