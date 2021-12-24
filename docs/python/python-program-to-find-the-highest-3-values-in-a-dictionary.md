# Python 程序查找字典中最高的 3 个值

> 原文:[https://www . geesforgeks . org/python-program-to-find-最高 3 值 in-a-dictionary/](https://www.geeksforgeeks.org/python-program-to-find-the-highest-3-values-in-a-dictionary/)

[Python 中的 Dictionary](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key:value pair。

**示例:**

```py
Input : my_dict = {'A': 67, 'B': 23, 'C': 45,
                   'D': 56, 'E': 12, 'F': 69} 

Output : {'F': 69, 'A': 67, 'D': 56}
```

让我们看看不同的方法，我们可以在字典中找到最高的 3 个值。

**方法#1:** 使用[集合。计数器()](https://www.geeksforgeeks.org/counters-in-python-set-1/)
一个**计数器**是一个字典子类，用于计数易腐烂的物体。这是一个无序的集合，其中元素存储为字典键，它们的计数存储为字典值。计数可以是任何整数值，包括零或负计数。计数器类类似于其他语言中的包或多集。
most_common([n])返回一个列表，其中列出了 *n* 个最常见的元素以及它们从最常见到最不常见的计数。

## 蟒蛇 3

```py
# Python program to demonstrate
# finding 3 highest values in a Dictionary

from collections import Counter

# Initial Dictionary
my_dict = {'A': 67, 'B': 23, 'C': 45,
           'D': 56, 'E': 12, 'F': 69}

k = Counter(my_dict)

# Finding 3 highest values
high = k.most_common(3)

print("Initial Dictionary:")
print(my_dict, "\n")

print("Dictionary with 3 highest values:")
print("Keys: Values")

for i in high:
    print(i[0]," :",i[1]," ")
```

**Output:** 

```py
Initial Dictionary:
{'C': 45, 'B': 23, 'D': 56, 'A': 67, 'E': 12, 'F': 69} 

Dictionary with 3 highest values:
Keys: Values
F  : 69  
A  : 67  
D  : 56
```

**方法 2:** 使用 heapq.nlargest()

## 蟒蛇 3

```py
# Python program to demonstrate
# finding 3 highest values in a Dictionary
from heapq import nlargest

# Initial Dictionary
my_dict = {'A': 67, 'B': 23, 'C': 45,
           'D': 56, 'E': 12, 'F': 69}

print("Initial Dictionary:")
print(my_dict, "\n")

ThreeHighest = nlargest(3, my_dict, key = my_dict.get)

print("Dictionary with 3 highest values:")
print("Keys: Values")

for val in ThreeHighest:
    print(val, ":", my_dict.get(val))
```

**Output:** 

```py
Initial Dictionary:
{'D': 56, 'E': 12, 'F': 69, 'C': 45, 'B': 23, 'A': 67} 

Dictionary with 3 highest values:
Keys: Values
F : 69
A : 67
D : 56
```