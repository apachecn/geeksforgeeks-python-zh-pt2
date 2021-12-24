# Python 元组方法

> 原文:[https://www.geeksforgeeks.org/python-tuple-methods/](https://www.geeksforgeeks.org/python-tuple-methods/)

[**【Python 元组】**](https://www.geeksforgeeks.org/python-tuples/) 是更像列表的不可变集合。Python 提供了一些处理元组的方法。在本文中，我们将借助一些例子详细讨论这两种方法。

## 计数()方法

Tuple 的 count()方法返回给定元素在元组中出现的次数。

**语法:**

```
tuple.count(element)
```

其中元素是要计数的元素。

**示例 1:使用 Tuple count()方法**

## python 3

```
# Creating tuples
Tuple1 = (0, 1, 2, 3, 2, 3, 1, 3, 2)
Tuple2 = ('python', 'geek', 'python', 
          'for', 'java', 'python')

# count the appearance of 3
res = Tuple1.count(3)
print('Count of 3 in Tuple1 is:', res)

# count the appearance of python
res = Tuple2.count('python')
print('Count of Python in Tuple2 is:', res)
```

**输出:**

```
Count of 3 in Tuple1 is: 3
Count of Python in Tuple2 is: 3
```

**示例 2:在元组中计数元组和列表作为元素**

## python 3

```
# Creating tuples
Tuple = (0, 1, (2, 3), (2, 3), 1, 
         [3, 2], 'geeks', (0,))

# count the appearance of (2, 3)
res = Tuple.count((2, 3))
print('Count of (2, 3) in Tuple is:', res)

# count the appearance of [3, 2]
res = Tuple.count([3, 2])
print('Count of [3, 2] in Tuple is:', res)
```

**输出:**

```
Count of (2, 3) in Tuple is: 2
Count of [3, 2] in Tuple is: 1
```

## 索引()方法

Index()方法返回元组中给定元素的第一次出现。

**语法:**

```
tuple.index(element, start, end)
```

**参数:**

*   **Element:** The element to be searched.
*   **Start (optional):** The starting index from the place where the search starts.
*   **End (optional):** The ending index of the place where the search is completed.

**注意:**如果在元组中找不到元素，此方法将引发 ValueError。

**示例 1:使用元组索引()方法**

## python 3

```
# Creating tuples
Tuple = (0, 1, 2, 3, 2, 3, 1, 3, 2)

# getting the index of 3
res = Tuple.index(3)
print('First occurrence of 3 is', res)

# getting the index of 3 after 4th
# index
res = Tuple.index(3, 4)
print('First occurrence of 3 after 4th index is:', res)
```

**输出:**

```
First occurrence of 3 is 3
First occurrence of 3 after 4th index is: 5
```

**例 2:元素未找到时使用 Tuple()方法**

## python 3

```
# Creating tuples
Tuple = (0, 1, 2, 3, 2, 3, 1, 3, 2)

# getting the index of 3
res = Tuple.index(4)
```

**输出:**

```
ValueError: tuple.index(x): x not in tuple
```

**注意:**关于 Python 元组的更多信息，请参考 [Python 元组教程](https://www.geeksforgeeks.org/python-tuples/)。