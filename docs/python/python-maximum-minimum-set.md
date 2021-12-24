# Python |集合中的最大值和最小值

> 原文:[https://www.geeksforgeeks.org/python-maximum-minimum-set/](https://www.geeksforgeeks.org/python-maximum-minimum-set/)

在本文中，我们将学习如何使用 Python 的内置函数在 Python 中获取集合中的最大和最小元素。
示例:

```
Input : set = ([8, 16, 24, 1, 25, 3, 10, 65, 55])
Output : max is 65

Input : set = ([4, 12, 10, 9, 4, 13])
Output : min is 4

```

**一组中的最大值()**

Python 中的内置函数 max()用于获取集合中所有元素的最大值。

```
# Python code to get the maximum element from a set
def MAX(sets):
    return (max(sets))

# Driver Code
sets = set([8, 16, 24, 1, 25, 3, 10, 65, 55])
print(MAX(sets))
```

输出:

```
65

```

**一组中的最小()**

```
# Python code to get the minimum element from a set
def MIN(sets):
    return (min(sets))

# Driver Code
sets = set([4, 12, 10, 9, 4, 13])
print(MIN(sets))
```

输出:

```
4

```