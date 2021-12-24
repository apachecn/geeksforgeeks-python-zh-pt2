# Python 中的常规字典与有序字典

> 原文:[https://www . geesforgeks . org/regular-dictionary-vs-ordered-dictionary-in-python/](https://www.geeksforgeeks.org/regular-dictionary-vs-ordered-dictionary-in-python/)

[Python 中的 Dictionary](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key:value pair。字典中提供了键值，以使其更加优化。常规字典类型不跟踪(键、值)对的插入顺序，因此根据它们在哈希表中的存储方式遍历键，哈希表又基于随机值，以减少冲突。
与此相反，Python 提供了 [OrderedDict](https://www.geeksforgeeks.org/ordereddict-in-python/) 类型，它会记住字典中(键、值)对的插入顺序，从而保持顺序。OrderedDict 比 Python 中的常规字典消耗更多的内存，因为底层的双链接列表实现可以保持顺序。

**示例:**

## 计算机编程语言

```
# A Python program to demonstrate
# the difference between regular
# and ordered dictionary.

import collections

# Creating a regular dictionary
print('Regular dictionary:')
d = {chr(k):k for k in range(ord('a'), ord('g'))}

for k, v in d.items():
    print(k, v)

# Creating an Ordered dictionary
print('\nOrderedDict:')
d = collections.OrderedDict()
[d.setdefault(chr(k), k) for k in range(ord('a'), ord('g'))]

for k, v in d.items():
    print(k, v)
```

**输出:**

```
Regular dictionary:
('a', 97)
('c', 99)
('b', 98)
('e', 101)
('d', 100)
('f', 102)

OrderedDict:
('a', 97)
('b', 98)
('c', 99)
('d', 100)
('e', 101)
('f', 102)
```

**注意:**从 Python 3.7 开始，保证 Python 字典的插入顺序。

**删除并重新插入:**
删除并重新插入同一个键会将其按顺序推到后面，但会保持插入顺序。

**示例:**

## 计算机编程语言

```
# A Python program to demonstrate
# working of deletion and re-insertion in
# regular and OrderedDict

from collections import OrderedDict

print("Before deleting:\n")

d = {}
print("Regular dictionary:")
d['a'] = 1
d['b'] = 2
d['c'] = 3
d['d'] = 4
for key, value in d.items():
    print(key, value)

od = OrderedDict()
print("\nOrdered dictionary:")
od['a'] = 1
od['b'] = 2
od['c'] = 3
od['d'] = 4
for key, value in od.items():
    print(key, value)

print("\nAfter deleting:\n")

print("Regular dictionary:")
d.pop('c')
for key, value in d.items():
    print(key, value)

print("\nOrdered dictionary:")
od.pop('c')
for key, value in od.items():
    print(key, value)

print("\nAfter re-inserting:\n")

print("Regular dictionary:")
d['c'] = 3
for key, value in d.items():
    print(key, value)

print("\nOrdered dictionary:")
od['c'] = 3
for key, value in od.items():
    print(key, value)
```

**输出:**

```
Before deleting:

Regular dictionary:
('a', 1)
('c', 3)
('b', 2)
('d', 4)

Ordered dictionary:
('a', 1)
('b', 2)
('c', 3)
('d', 4)

After deleting:

Regular dictionary:
('a', 1)
('b', 2)
('d', 4)

Ordered dictionary:
('a', 1)
('b', 2)
('d', 4)

After re-inserting:

Regular dictionary:
('a', 1)
('c', 3)
('b', 2)
('d', 4)

Ordered dictionary:
('a', 1)
('b', 2)
('d', 4)
('c', 3)
```