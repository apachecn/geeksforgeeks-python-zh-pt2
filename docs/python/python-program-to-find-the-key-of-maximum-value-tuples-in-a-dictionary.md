# Python 程序在字典中查找最大值元组的关键字

> 原文:[https://www . geesforgeks . org/python-program-to-find-key-of-max-value-tuples-in-a-dictionary/](https://www.geeksforgeeks.org/python-program-to-find-the-key-of-maximum-value-tuples-in-a-dictionary/)

给定一个以值为元组的字典，任务是编写一个 python 程序来找到最大值元组的键。

**示例:**

> **输入:**test _ dict = { ' gfg ':(“a”，3)、“is”:(“c”，9)、“best”:(“k”，10)、“for”:(“p”，11)、“geeks”:(‘m’，2)}
> 
> **输出:**为
> 
> **说明:** 11 为元组的最大值，为关键字“for”。
> 
> **输入:**test _ dict = { ' gfg ':(“a”，13)、“is”:(“c”，9)、“best”:(“k”，10)、“for”:(“p”，1)、“geeks”:(“m”，2)}
> 
> **输出:** gfg
> 
> **说明:** 13 为元组的最大值，为关键字“gfg”。

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**值()**](https://www.geeksforgeeks.org/python-dictionary-values/)**+**[**next()**](https://www.geeksforgeeks.org/python-next-method/)

在这种情况下，使用 max()找到所有元组值的最大值，并使用 values()提取值。下一个()，用于使用访问的迭代器方法进行迭代，并将每个元组值与最大值进行比较。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum tuple value key
# Using max() + values() + next()

# initializing dictionary
test_dict = {'gfg': ("a", 3), 'is': ("c", 9), 'best': (
    "k", 10), 'for': ("p", 11), 'geeks': ('m', 2)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# getting maximum value
max_val = max(test_dict.values(), key=lambda sub: sub[1])

# getting key with maximum value using comparison
res = next(key for key, val in test_dict.items() if val == max_val)

# printing result
print("The maximum key : " + str(res))
```

**输出:**

> 原词典为:{'gfg': ('a '，3)、' is': ('c '，9)、' best': ('k '，10)、' for': ('p '，11)、' geeks': ('m '，2)}
> 
> 最大键:用于

**方法 2:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**值()**](https://www.geeksforgeeks.org/python-dictionary-values/)

在本文中，我们使用列表理解来执行获取所有最大匹配值的任务。获取最大值是使用 max()完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum tuple value key
# Using list comprehension + max() + values()

# initializing dictionary
test_dict = {'gfg': ("a", 3), 'is': ("c", 9), 'best': (
    "k", 10), 'for': ("p", 11), 'geeks': ('m',  2)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# getting maximum value
max_val = max(test_dict.values(), key=lambda sub: sub[1])

# getting key with maximum value using comparison
res = [key for key, val in test_dict.items() if val == max_val][0]

# printing result
print("The maximum key : " + str(res))
```

**输出:**

> 原词典为:{'gfg': ('a '，3)、' is': ('c '，9)、' best': ('k '，10)、' for': ('p '，11)、' geeks': ('m '，2)}
> 
> 最大键:用于