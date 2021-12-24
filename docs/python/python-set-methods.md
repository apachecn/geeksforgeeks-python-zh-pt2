# Python 设置方法

> 原文:[https://www.geeksforgeeks.org/python-set-methods/](https://www.geeksforgeeks.org/python-set-methods/)

Python 中的 [**集合**](https://www.geeksforgeeks.org/sets-in-python/) 是一个无序且可变的独特元素的集合。Python 提供了各种函数来使用 Set。在本文中，我们将看到 Python 提供的处理集合的所有函数的列表。

## 添加和删除元素

我们可以在以下功能的帮助下添加和删除集合中的元素–

*   [**add():**](https://www.geeksforgeeks.org/set-add-python/) 将给定元素添加到集合中
*   [**清除():**](https://www.geeksforgeeks.org/set-clear-python/) 从集合中移除所有元素
*   **丢弃():**从集合中移除元素
*   [**pop():**](https://www.geeksforgeeks.org/python-set-pop/) 从集合中返回并移除随机元素
*   **移除():**从集合中移除元素

**示例:**在集合中添加和移除元素。

## 蟒蛇 3

```
# set of letters
s = {'g', 'e', 'k', 's'}

# adding 's'
s.add('f')
print('Set after updating:', s)

# Discarding element from the set
s.discard('g')
print('\nSet after updating:', s)

# Removing element from the set
s.remove('e')
print('\nSet after updating:', s)

# Popping elements from the set
print('\nPopped element', s.pop())
print('Set after updating:', s)

s.clear()
print('\nSet after updating:', s)
```

**Output**

```
Set after updating: {'g', 'k', 's', 'e', 'f'}

Set after updating: {'k', 's', 'e', 'f'}

Set after updating: {'k', 's', 'f'}

Popped element k
Set after updating: {'s', 'f'}

Set after updating: set()
```

## Python 集合方法表

<figure class="table">

| 功能名称 | 描述 |
| --- | --- |
| [添加()](https://www.geeksforgeeks.org/set-add-python/) | 将给定元素添加到集合中 |
| [晴()](https://www.geeksforgeeks.org/set-clear-python/) | 从集合中移除所有元素 |
| [副本()](https://www.geeksforgeeks.org/set-copy-python/) | 返回集合的浅拷贝 |
| [差异()](https://www.geeksforgeeks.org/python-set-difference/) | 返回两个集合之差的集合 |
| [差异 _ 更新()](https://www.geeksforgeeks.org/python-set-difference_update/) | 用两个集合之间的差异更新现有的调用者集合 |
| 丢弃() | 从集合中移除元素 |
| [frozenset()](https://www.geeksforgeeks.org/frozenset-in-python/) | 返回一个不可变的 frozenset 对象 |
| [交点()](https://www.geeksforgeeks.org/intersection-function-python/) | 返回一个集合，该集合包含所有集合的交集 |
| 交集 _ 更新() | 用集合的交集更新现有的调用者集合 |
| isdisjoint() | 检查集合是否不相交 |
| [isssubset()](https://www.geeksforgeeks.org/issubset-in-python/) | 如果集合 A 的所有元素都存在于另一个集合 B 中，则返回 True |
| [这是上集()](https://www.geeksforgeeks.org/issuperset-in-python/) | 如果集合 A 的所有元素都占据集合 B，则返回真 |
| [pop()](https://www.geeksforgeeks.org/python-set-pop/) | 从集合中返回并移除随机元素 |
| 移除() | 从集合中移除元素 |
| [对称 _ 差()](https://www.geeksforgeeks.org/python-set-symmetric_difference/) | 返回两个集合之间的对称差 |
| [对称 _ 差异 _ 更新()](https://www.geeksforgeeks.org/python-set-symmetric-difference-update/) | 用集合的对称差更新现有调用方集合 |
| [union()](https://www.geeksforgeeks.org/union-function-python/) | 返回一个集合，该集合包含所有集合的并集 |
| [更新()](https://www.geeksforgeeks.org/python-set-update/) | 向集合中添加元素 |

</figure>

**注意:**关于 Python 集的更多信息，请参考 [Python 集教程](https://www.geeksforgeeks.org/sets-in-python/)。