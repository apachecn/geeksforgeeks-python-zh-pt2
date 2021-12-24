# Python–删除任何非必需字符的字符串

> 原文:[https://www . geesforgeks . org/python-remove-strings-with-any-non-required-character/](https://www.geeksforgeeks.org/python-remove-strings-with-any-non-required-character/)

给定一个字符串列表，删除字符串，如果它包含任何不需要的字符。

> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“geeks”]，chr _ list =[“f”、“m”、“n”、“I”]
> **输出**:[“best”、“geeks”]
> **解释**:给定字符串不包含 f、m、n 或 I
> 
> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“geeks”]，chr _ list =[“f”、“m”、“n”]
> **输出**:[“best”、“geeks”、“is”]
> **解释**:给定字符串不包含 f、m 或 n

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**任意()**](https://www.geeksforgeeks.org/any-all-in-python/)

在这种情况下，我们测试所有字符串，并使用 any()迭代所有非必需字符列表，并检查它在字符串中的存在，如果找到，该列表不包括在结果列表中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove strings with any non-required character
# Using list comprehension + any()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# non-required char list
chr_list = ['f', 'm', 'n', 'i']

# checking for all strings
# removing if contains even 1 character
res = [sub for sub in test_list if not any(ele in sub for ele in chr_list)]

# printing result
print("Filtered Strings : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Filtered Strings : ['best', 'geeks']

```

**方法 2:使用过滤器()+ lambda + any()**

在本文中，我们使用 filter()和 lambda 函数执行过滤任务。Rest any()用于检查字符串中是否存在要删除的字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove strings with any non-required character
# Using filter() + lambda + any()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# non-required char list
chr_list = ['f', 'm', 'n', 'i']

# checking for all strings
# filter and lambda used to do this task
res = list(filter(lambda sub: not any(
    ele in sub for ele in chr_list), test_list))

# printing result
print("Filtered Strings : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Filtered Strings : ['best', 'geeks']

```