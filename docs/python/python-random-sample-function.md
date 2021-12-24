# Python | random.sample()函数

> 原文:[https://www . geesforgeks . org/python-random-sample-function/](https://www.geeksforgeeks.org/python-random-sample-function/)

****sample()**** 是 Python 中 ****随机模块**** 的内置函数，返回从序列中选择的特定长度的项目列表，即列表、元组、字符串或集合。用于随机取样，无需更换。

> **语法:**随机样本(序列，k)
> 
> **参数:**
> **序列**:可以是列表、元组、字符串或集合。
> **k** :整数值，指定样本的长度。
> 
> **返回:** k 长度从序列中选择的新元素列表。

**代码# 1:**sample()函数的简单实现。

```
# Python3 program to demonstrate
# the use of sample() function .

# import random 
from random import sample

# Prints list of random items of given length
list1 = [1, 2, 3, 4, 5] 

print(sample(list1,3))
```

**输出:**

```
[2, 3, 5]
```

**代码#2:** 样本()函数的基本用法。

```
# Python3 program to demonstrate
# the use of sample() function .

# import random 
import random

# Prints list of random items of
# length 3 from the given list.
list1 = [1, 2, 3, 4, 5, 6] 
print("With list:", random.sample(list1, 3))

# Prints list of random items of
# length 4 from the given string. 
string = "GeeksforGeeks"
print("With string:", random.sample(string, 4))

# Prints list of random items of
# length 4 from the given tuple.
tuple1 = ("ankit", "geeks", "computer", "science",
                   "portal", "scientist", "btech")
print("With tuple:", random.sample(tuple1, 4))

# Prints list of random items of
# length 3 from the given set.
set1 = {"a", "b", "c", "d", "e"}
print("With set:", random.sample(set1, 3))
```

**输出:**

```
With list: [3, 1, 2]
With string: ['e', 'f', 'G', 'G']
With tuple: ['ankit', 'portal', 'geeks', 'computer']
With set: ['b', 'd', 'c']
```

**注意:**每次输出都会有所不同，因为它会返回一个随机项目。

**代码#3:** 引发异常

如果样本量(即 k)大于序列量，则会出现*值错误*。

```
# Python3 program to demonstrate the
# error of sample() function.
import random

list1 = [1, 2, 3, 4] 

# exception raised
print(random.sample(list1, 5)) 
```

**输出:**

```
Traceback (most recent call last):
  File "C:/Users/user/AppData/Local/Programs/Python/Python36/all_prgm/geeks_article/sample_method_article.py", line 8, in 
    print(random.sample(list1, 5))
  File "C:\Users\user\AppData\Local\Programs\Python\Python36\lib\random.py", line 317, in sample
    raise ValueError("Sample larger than population or is negative")
ValueError: Sample larger than population or is negative

```