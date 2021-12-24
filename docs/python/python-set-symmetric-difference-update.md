# Python 设置对称 _ 差异 _ 更新()

> 原文:[https://www . geesforgeks . org/python-set-对称-差异-更新/](https://www.geeksforgeeks.org/python-set-symmetric-difference-update/)

两个集合的对称差是两个集合中任何一个集合的元素集合，而不是两个集合的元素集合。

![symmetric-difference](img/14dac6f9c94ca441da1d35dac3d3e111.png)

对称差用绿色标记
[对称 _ 差()](https://www.geeksforgeeks.org/python-set-symmetric_difference-2/)方法返回一个包含两个集合的对称差的新集合。symmetric_difference_update()方法使用集合的对称差来更新调用 symmetric_difference_update()的集合。

> **语法:**
> a . symmetric _ difference _ update(B)
> **参数:**
> symmetric _ difference 以单个“可迭代”为自变量。Iterable 应该包含 hashable 对象。
> **返回:**
> 该方法返回无(表示没有返回值)。它只使用集合的对称差更新调用对称差更新()的集合。

**代码 1**

## 计算机编程语言

```py
# Python code to demonstrate working of
# symmetric_difference_update()

A = {'p', 'a', 'w', 'a', 'n'}
B = {'r', 'a', 'o', 'n', 'e'}

# result is always none.
result = A.symmetric_difference_update(B)

print('A = ', A)
print('B = ', B)
print('result = ', result)
```

**输出:**

```py
('A = ', set(['e', 'o', 'p', 'r', 'w']))
('B = ', set(['a', 'r', 'e', 'o', 'n']))
('result = ', None)

```

**代码 2**

## 计算机编程语言

```py
# Python code to demonstrate working of
# symmetric_difference_update()

A = {'s', 'u', 'n', 'n', 'y'}
B = {'b', 'u', 'n', 'n', 'y'}

# result is always none.
result = A.symmetric_difference_update(B)

print('A = ', A)
print('B = ', B)
print('result = ', result)
```

**输出:**

```py
('A = ', set(['s', 'b']))
('B = ', set(['y', 'b', 'u', 'n']))
('result = ', None)

```

**代码 3:**

## 计算机编程语言

```py
# Python code to demonstrate working of
# symmetric_difference_update()

A = {1, 2, 3, 4, 5, 6}
B = [4, 5, 7, 8]

# passing argument as list

A.symmetric_difference_update(B)
print("A =", A)

A = {2, 4, 6, 8}
B = (i for i in range(2, 6))

# passing argument as generator object

A.symmetric_difference_update(B)
print("A=", A)
```

**Output**

```py
('A =', set([1, 2, 3, 6, 7, 8]))
('A=', set([3, 5, 6, 8]))

```

**代码 4:**

## 计算机编程语言

```py
# Python code to demonstrate working of
# symmetric_difference_update()

A = {1, 2, 3, 4, 5}
B = [[1, 2, 3], 4, 5]

# error as b contain one element as list(unhashable object)

A.symmetric_difference_update(B)
print("A =", A)
```

**输出**

```py
Traceback (most recent call last):
  File "/home/1b4e24cadc3fabcd5f90141964a60e9b.py", line 9, in <module>
    A.symmetric_difference_update(B)
TypeError: unhashable type: 'list'

```