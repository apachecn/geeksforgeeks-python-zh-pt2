# Python–按最大频率字符排序字符串

> 原文:[https://www . geesforgeks . org/python-按最大频率字符串排序-字符/](https://www.geeksforgeeks.org/python-sort-strings-by-maximum-frequency-character/)

给定一个字符串，任务是编写一个 Python 程序来执行按最大出现字符排序。

> **输入** : test_list = [“极客伪造者”、“更好的”、“为”、“极客”]
> **输出** : [“为”、“极客”、“更好的”、“极客伪造者”]
> **解释** : 1 < 2 < 3 < 4，是字符出现频率最大的排序。
> 
> **输入** : test_list =【“极客伪造者”“为”“极客”】
> **输出**:【“为”“极客”“极客伪造者”】
> **解释** : 1 < 2 < 4，是最大字符出现频率的排序。

**方法#1 :** 使用 sort() + Counter() + [max()](https://www.geeksforgeeks.org/python-max-function/)

在本文中，我们使用 sort()执行就地排序，Counter()用于计算字符频率，max()用于获得计算频率的最大值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Strings by maximum frequency character
# Using sort() + Counter() + max()
from collections import Counter

# getting maximum character frequency
def max_freq(arg_str):
    res = Counter(arg_str) 
    return arg_str.count(max(res, key = res.get))

# initializing list
test_list = ["geekforgeeks", "bettered", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# performing sort 
test_list.sort(key = max_freq)

# printing result 
print("Sorted List : " + str(test_list))
```

**输出:**

```
The original list is : ['geekforgeeks', 'bettered', 'for', 'geeks']
Sorted List : ['for', 'geeks', 'bettered', 'geekforgeeks']
```

**方法 2 :** 使用[排序()](https://www.geeksforgeeks.org/sorted-function-python/)+[λ](https://www.geeksforgeeks.org/python-lambda/)+计数器()

在本例中，我们使用 sorted()和 lambda 函数执行排序任务，以获得单个语句逻辑表达式，从而避免外部函数调用。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Strings by maximum frequency character
# Using sorted() + lambda + Counter()
from collections import Counter

# getting maximum character frequency
def max_freq(arg_str):
    res = Counter(arg_str) 
    return arg_str.count(max(arg_str, key = arg_str.get))

# initializing list
test_list = ["geekforgeeks", "bettered", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# performing sort 
# lambda function to drive logic
res = sorted(test_list, 
             key = lambda arg_str : arg_str.count(
               max(Counter(arg_str), key = Counter(arg_str).get)))

# printing result 
print("Sorted List : " + str(res))
```

**输出:**

```
The original list is : ['geekforgeeks', 'bettered', 'for', 'geeks']
Sorted List : ['for', 'geeks', 'bettered', 'geekforgeeks']
```