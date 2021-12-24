# Python 分类容器|简介

> 原文:[https://www . geesforgeks . org/python-sorted-containers-an-introduction/](https://www.geeksforgeeks.org/python-sorted-containers-an-introduction/)

**排序容器**是一个 Apache2 许可的排序集合库，用纯 Python 编写，作为 C 扩展速度很快。它由格兰特·詹克斯创建，是一个开源库。它是容器的集合，允许我们非常有效地插入和移除元素，同时保持排序顺序。

**特征:**

*   纯 Python
*   完全记录在案
*   基准比较(备选方案、运行时、负载系数
*   性能(通常比 C 实现更快)
*   兼容的应用编程接口(与流行的 blist 和 rbtree 模块几乎相同)
*   功能丰富(例如，获取排序字典中最大的五个键:d.iloc[-5:])
*   实用设计(例如，排序集是一个带有排序列表索引的 Python 集)

**容器:**

*   出去！出去
*   SortedDict
*   黑色套装

**安装:**

**Mac** 和 **Linux** 用户可以通过 pip 命令进行安装:

```py
 sudo pip install sortedcontainers 
```

## 排序列表-

排序列表是一个排序的可变序列，其中的值以排序的顺序维护。

**添加和删除元素的功能:**

> **add(value)** :以一个元素为参数，通过维护排序顺序插入列表的函数。*运行时复杂度:* O(log(n))
> 
> **update(iterable)** :一个函数，该函数将一个 iterable 作为输入，并通过添加来自 iterable *运行时复杂度的所有值来更新 sorted list:*O(k * log(n))。
> 
> **清除()**:从排序列表中移除所有值。*运行时复杂度:* O(n)。
> 
> **丢弃(值)**:如果值是成员，则从排序列表中移除值。如果 value 不是成员，则什么也不做。*运行时复杂度:* O(log(n))。

以下是实施–

```py
# importing libraries
from sortedcontainers import SortedList, SortedSet, SortedDict

# initializing a sorted list with parameters
# it takes an iterable as a parameter.
sorted_list = SortedList([1, 2, 3, 4])

# initializing a sorted list using default constructor
sorted_list = SortedList()

# inserting values one by one using add()
for i in range(5, 0, -1):
    sorted_list.add(i)

# prints the elements in sorted order
print('list after adding 5 elements: ', sorted_list)

print('list elements are: ', end = '')

# iterating through a sorted list
for i in sorted_list:
    print(i, end = ' ')
print()

# removing all elements using clear()
sorted_list.clear()

# adding elements using the update() function
elements = [10, 9, 8, 7, 6]

sorted_list.update(elements)

# prints the updated list in sorted order
print('list after updating: ', sorted_list)

# removing a particular element
sorted_list.discard(8)

print('list after removing one element: ', sorted_list)

# removing all elements
sorted_list.clear()

print('list after removing all elements using clear: ', sorted_list)
```

**输出:**

```py
list after adding 5 elements:  SortedList([1, 2, 3, 4, 5], load=1000)

list elements are: 1 2 3 4 5 

list after updating:  SortedList([6, 7, 8, 9, 10], load=1000)

list after removing one element:  SortedList([6, 7, 9, 10], load=1000)

list after removing all elements using clear:  SortedList([], load=1000)

```

## 黑色套装

有序集是一个有序的可变集，其中的值是唯一的，并以有序的顺序维护。排序集合使用集合进行集合运算，并维护一个排序的值列表。排序后的集合值必须是可散列和可比较的。

**添加和删除元素的功能:**

> **add(value) :** 以一个元素为参数，通过保持排序顺序将其插入集合的函数。*运行时复杂度:* O(log(n))
> 
> **清除()**:从排序的集合中移除所有值。*运行时复杂性:* O(n)
> 
> **丢弃(值)**:如果排序集是成员，则从排序集中移除值。如果 value 不是成员，则什么也不做。*运行时复杂度:* O(log(n))

```py
# importing libraries
from sortedcontainers import SortedList, SortedSet, SortedDict

# initializing a sorted set with parameters
# it takes an iterable as an argument
sorted_set = SortedSet([1, 1, 2, 3, 4])

# initializing a sorted set using default constructor
sorted_set = SortedSet()

# inserting values one by one
for i in range(5, 0, -1):
    sorted_set.add(i)

print('set after adding elements: ', sorted_set)

# inserting duplicate value
sorted_set.add(5)

print('set after inserting duplicate element: ', sorted_set)

# discarding an element
sorted_set.discard(4)

print('set after discarding: ', sorted_set)

# checking membership using 'in' operator
if(2 in sorted_set):
    print('2 is present')
else:
    print('2 is not present')

print('set elements are: ', end = '')

# iterating through a sorted set
for i in sorted_set:
    print(i, end = ' ')
print()
```

**输出:**

```py
set after adding elements:  SortedSet([1, 2, 3, 4, 5], key=None, load=1000)

set after inserting duplicate element:  SortedSet([1, 2, 3, 4, 5], key=None, load=1000)

set after discarding:  SortedSet([1, 2, 3, 5], key=None, load=1000)

2 is present

set elements are: 1 2 3 5

```

### sorted Dict–

Sorted dict 是一个排序的可变映射，其中键以排序的顺序维护。排序 dict 从 dict 继承来存储项目，并维护一个排序的键列表。排序后的字典键必须是可散列和可比较的。

**添加和删除元素的功能:**

> **设置默认值(键，默认值=无)**:排序字典中由键标识的项目的返回值。如果关键字在已排序的字典中，则返回它的值。如果键不在排序的字典中，则插入默认值的键并返回默认值。*运行时复杂度:* O(log(n))
> 
> **清除()**:从排序后的字典中移除所有值。*运行时复杂性:* O(n)
> 
> **get(key，默认)**:如果 key 在字典里，返回 key 的值，否则默认。

```py
# importing libraries
from sortedcontainers import SortedList, SortedSet, SortedDict

# initializing a sorted dict with parameters
# it takes a dictionary object as a parameter
sorted_dict = SortedDict({'a': 1, 'b': 2, 'c': 3})

# initializing a sorted dict
sorted_dict = SortedDict({'a': 1, 'c': 2, 'b':3})

# print the dict
print('sorted dict is: ', sorted_dict)

# adding key => value pairs
sorted_dict['d'] = 3

print('sorted dict after adding an element: ', sorted_dict)

# adding element using setdefault()
sorted_dict.setdefault('e', 4)

print('sorted dict after setdefault(): ', sorted_dict)

# using the get function
print('using the get function to print the value of a: ', sorted_dict.get('a', 0))

# checking membership using 'in' operator
if('a' in sorted_dict):
    print('a is present')
else:
    print('a is not present')

print('dict elements are: ', end = '')

# iterating over key => value pairs in a dictionary
for key in sorted_dict:
    print('{} -> {}'.format(key, sorted_dict[key]), end = ' ')
print()

# removing all elements from the dict
sorted_dict.clear()

print('sorted dict after removing all elements: ', sorted_dict)
```

**输出:**

```py
sorted dict is:  SortedDict(None, 1000, {'a': 1, 'b': 3, 'c': 2})

sorted dict after adding an element:  SortedDict(None, 1000, {'a': 1, 'b': 3, 'c': 2, 'd': 3})

sorted dict after setdefault():  SortedDict(None, 1000, {'a': 1, 'b': 3, 'c': 2, 'd': 3, 'e': 4})

using the get function to print the value of a:  1

a is present

dict elements are: a -> 1 b -> 3 c -> 2 d -> 3 e -> 4 

sorted dict after removing all elements:  SortedDict(None, 1000, {})

```

参考:[http://www.grantjenks.com/docs/sortedcontainers/index.html](http://www.grantjenks.com/docs/sortedcontainers/index.html)