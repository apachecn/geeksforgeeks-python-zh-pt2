# Python | Zipping 字典中两个不等长列表

> 原文:[https://www . geesforgeks . org/python-zipping-two-不等长词典列表/](https://www.geeksforgeeks.org/python-zipping-two-unequal-length-list-in-dictionary/)

给定两个长度可能不等的列表，任务是在字典中压缩两个列表，这样长度较短的列表将重复出现。

因为 Python 中的字典是键:值对的无序集合，所以结果将以无序的方式打印。

**方法#1:使用`itertools()`**

```py
# Python code to demonstrate
# return the sum of values of a dictionary
# with same keys in the list of dictionary

from itertools import cycle

# Initialising list of dictionary
ini_lis1 = ['a', 'b', 'c', 'd', 'e']
ini_lis2 = [1, 2, 3]

# zipping in cyclic if shorter length
result = dict(zip(ini_lis1, cycle(ini_lis2)))

# printing resultant dictionary
print("resultant dictionary : ", str(result))
```

**Output:**

```py
resultant dictionary :  {'b': 2, 'd': 1, 'c': 3, 'e': 2, 'a': 1}

```

**方法 2:使用字典理解**

```py
# Python code to demonstrate
# return the sum of values of dictionary
# with same keys in list of dictionary

from itertools import cycle

# Initialising list of dictionary
ini_lis1 = ['a', 'b', 'c', 'd', 'e']
ini_lis2 = [1, 2, 3]

# zipping in cyclic if shorter length
result = {v: ini_lis2[i % len(ini_lis2)] 
          for i, v in enumerate(ini_lis1)}

print("resultant dictionary : ", str(result))
```

**Output:**

```py
resultant dictionary :  {'d': 1, 'c': 3, 'e': 2, 'b': 2, 'a': 1}

```

**方法三:用得克()**

```py
# Python code to demonstrate
# return the sum of values of dictionary
# with same keys in list of dictionary

from collections import deque

# Initialising list of dictionary
ini_lis1 = ['a', 'b', 'c', 'd', 'e']
ini_lis2 = deque([1, 2, 3])

# zipping in cyclic if shorter length
result = {}
for letter in ini_lis1:
    number = ini_lis2.popleft()
    result[letter] = number
    ini_lis2.append(number)

print("resultant dictionary : ", str(result))
```

**Output:**

```py
resultant dictionary :  {'c': 3, 'd': 1, 'b': 2, 'e': 2, 'a': 1}

```