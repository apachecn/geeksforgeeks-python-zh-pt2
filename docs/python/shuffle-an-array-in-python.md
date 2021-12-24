# 在 Python 中洗牌一个数组

> 原文:[https://www.geeksforgeeks.org/shuffle-an-array-in-python/](https://www.geeksforgeeks.org/shuffle-an-array-in-python/)

洗牌一直是一个有用的工具，它只不过是重新排列一个数组中的元素。知道多种方法来实现这一点总是有好处的。让我们讨论一下实现这一点的某些方法。

**方法 1:** 在这个方法中我们使用*shuffle()***T5】方法从 *numpy* 库中获取。**

 **## 蟒 3** 

```
# Import required module
import numpy as np

# Assign array
arr = np.array([1, 2, 3, 4, 5, 6])

# Display original array
print("Original array: ", arr)

# Shuffle array
np.random.shuffle(arr)

# Display shuffled array
print("Shuffled array: ", arr)
```