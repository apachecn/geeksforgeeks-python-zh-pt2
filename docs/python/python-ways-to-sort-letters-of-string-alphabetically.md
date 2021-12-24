# Python |字符串字母按字母顺序排序的方法

> 原文:[https://www . geesforgeks . org/python-字符串字母排序方法/](https://www.geeksforgeeks.org/python-ways-to-sort-letters-of-string-alphabetically/)

给定一串字母，编写一个 python 程序，按照字母顺序对给定的字符串进行排序。

**示例:**

```
Input : PYTHON
Output : HNOPTY

Input : Geeks
Output : eeGks

```

#### 当字符串处于相同情况时–

**方法 1 :** 使用`sorted()`配合`join()`

```
# Python3 program to sort letters 
# of string alphabetically

def sortString(str):
    return ''.join(sorted(str))

# Driver code
str = 'PYTHON'
print(sortString(str))
```

**Output:**

```
HNOPTY

```

**方法 2 :** 使用`sorted()`配合`accumulate()`

```
# Python3 program to sort letters 
# of string alphabetically
from itertools import accumulate

def sortString(str):
    return tuple(accumulate(sorted(str)))[-1]

# Driver code
str = 'PYTHON'
print(sortString(str))
```

**Output:**

```
HNOPTY

```

**方法 3 :** 使用`sorted()`配合`reduce()`

另一种选择是使用 *reduce()* 方法。它使用“+”运算符对排序列表应用联接函数。

```
# Python3 program to sort letters 
# of string alphabetically
from functools import reduce

def sortString(str):
    return reduce(lambda a, b : a + b, sorted(str))

# Driver code
str = 'PYTHON'
print(sortString(str))
```

**Output:**

```
HNOPTY

```

#### 当字符串处于不同情况时–

使用`sorted()`和`join()`

```
# Python3 program to sort letters 
# of string alphabetically
from itertools import accumulate

def sortString(str):
    return "".join(sorted(str, key = lambda x:x.lower()))

# Driver code
str = 'Geeks'
print(sortString(str))
```

**Output:**

```
eeGks

```