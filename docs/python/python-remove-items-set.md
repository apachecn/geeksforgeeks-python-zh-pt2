# Python |从集合中移除项目

> 原文:[https://www.geeksforgeeks.org/python-remove-items-set/](https://www.geeksforgeeks.org/python-remove-items-set/)

在本文中，我们将尝试一种方法，通过这种方法可以按顺序从集合中移除元素。在开始之前，让我们先了解集合各种特征。集合是一种无序的集合数据类型，它是可迭代的、可变的，并且没有重复的元素。Python 的集合类代表了集合的数学概念。与列表相比，使用集合的主要优点是，它有一个高度优化的方法来检查集合中是否包含特定元素。

示例:

```
Input : set([12, 10, 13, 15, 8, 9])
Output :
{9, 10, 12, 13, 15}
{10, 12, 13, 15}
{12, 13, 15}
{13, 15}
{15}
set()

Input : set(['a','b','c','d','e'])
Output :
{'d', 'c', 'a', 'b'}
{'c', 'a', 'b'}
{'a', 'b'}
{'b'}
set()

```

**使用 pop()方法**
pop()是 Python 中的一个内置方法，用于从集合中逐个弹出或移除元素。首先移除集合中最小的元素，然后以递增的顺序移除元素。在下面的程序中，while 循环继续逐个移除元素，直到集合为空。

```
# Python program to remove elements from set
# Using the pop() method
def Remove(initial_set):
    while initial_set:
        initial_set.pop()
        print(initial_set)

# Driver Code
initial_set = set([12, 10, 13, 15, 8, 9])
Remove(initial_set)
```

输出:

```
{9, 10, 12, 13, 15}
{10, 12, 13, 15}
{12, 13, 15}
{13, 15}
{15}
set()

```