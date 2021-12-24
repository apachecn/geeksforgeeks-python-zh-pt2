# Python 程序将集合转换为元组，元组转换为集合

> 原文:[https://www . geesforgeks . org/python-program-convert-set-to-tuple-tuple-to-set/](https://www.geeksforgeeks.org/python-program-to-convert-set-into-tuple-and-tuple-into-set/)

让我们看看如何将集合转换为元组，并将元组转换为集合。为了执行任务，我们使用了一些方法，如 tuple()，set()，type()。

*   **tuple()** : tuple 方法用于转换为 tuple。此方法接受其他类型值作为参数，并返回元组类型值。
*   **set()** : set 方法是将其他类型值转换为 set 这个方法也是接受其他类型值作为参数并返回一个 set 类型值。
*   [**type()** :](https://www.geeksforgeeks.org/python-type-function/) type 方法帮助程序员检查值的数据类型。此方法接受一个值作为参数，并返回该值的类型。

**示例:**

```py
Input: {'a', 'b', 'c', 'd', 'e'}
Output: ('a', 'c', 'b', 'e', 'd')
Explanation: converting Set to tuple

Input: ('x', 'y', 'z')
Output: {'z', 'x', 'y'}
Explanation: Converting tuple to set

```

**示例 1:** 将集合转换为元组。

## 计算机编程语言

```py
#   program to convert set to tuple
# create set
s = {'a', 'b', 'c', 'd', 'e'}

# print set
print(type(s), " ", s)

# call tuple() method 
# this method convert set to tuple
t = tuple(s)

# print tuple
print(type(t), " ", t)
```

**输出:**

```py
<class 'set'>   {'a', 'c', 'b', 'e', 'd'}
<class 'tuple'>   ('a', 'c', 'b', 'e', 'd')

```

**示例 2:** 元组进入集合。

## 计算机编程语言

```py
#program to convert tuple into set

# create tuple
t = ('x', 'y', 'z')

# print tuple
print(type(t), "  ", t)

# call set() method
s = set(t)

# print set
print(type(s), "  ", s)
```

**输出:**

```py
<class 'tuple'>    ('x', 'y', 'z')
<class 'set'>    {'z', 'x', 'y'}

```