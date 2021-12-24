# Python–字符串中可能的子字符串计数

> 原文:[https://www . geesforgeks . org/python-可能-子串-从字符串中计数/](https://www.geeksforgeeks.org/python-possible-substring-count-from-string/)

给定目标字符串和参数子字符串，计算可以使用字符串构造多少子字符串，不允许重复。

> **输入**:test _ str =“geksefokesgergeks”，arg_str =“极客”
> **输出** : 3
> **解释**:“极客”可以使用字符串创建 3 次。
> 
> **输入**:test _ str =“geforksefkesgergeeks”，arg _ str =“for”
> **输出** : 2
> **解释**:“for”可以使用字符串创建 2 次。

**方法#1:使用计数()+分钟()+设置()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们将 arg 字符串的每个元素的计数除以目标字符串字符的计数，并使用 min()，返回最低的元素。背后的逻辑是，任何高于 min 的元素都意味着从该字符串开始，最小元素将丢失。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Possible Substring count from String
# Using min() + list comprehension + count()

# initializing string
test_str = "gekseforgeeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing arg string
arg_str = "geeks"

# using min and count to get minimum possible
# occurrence of character
res = min(test_str.count(char) // arg_str.count(char) for char in set(arg_str))

# printing result
print("Possible substrings count : " + str(res))
```

**Output**

```
The original string is : gekseforgeeks
Possible substrings count : 2
```

**方法二:使用 Counter() +列表理解**

这是执行这项任务的另一种方式。在本例中，我们使用 Counter()执行计数任务，列表理解用于将结果绑定在一起，使用 min()执行与前面方法类似的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Possible Substring count from String
# Using Counter() + list comprehension
from collections import Counter

# initializing string
test_str = "gekseforgeeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing arg string
arg_str = "geeks"

# using Counter to get character frequencies
temp1 = Counter(test_str)
temp2 = Counter(arg_str)
res = min(temp1[char] // temp2[char] for char in temp2.keys())

# printing result
print("Possible substrings count : " + str(res))
```

**Output**

```
The original string is : gekseforgeeks
Possible substrings count : 2
```