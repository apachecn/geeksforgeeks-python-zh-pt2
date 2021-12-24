# 打印艾特肯数组的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到打印-aitkens-array/](https://www.geeksforgeeks.org/python-program-to-print-aitkens-array/)

给定一个数字 n，任务是将艾肯的数组打印到 n

**示例:**

```py
Input: 5
Output:
[1]
[1, 2]
[2, 3, 5]
[5, 7, 10, 15]
[15, 20, 27, 37, 52]

Input: 7
Output:
[1]
[1, 2]
[2, 3, 5]
[5, 7, 10, 15]
[15, 20, 27, 37, 52]
[52, 67, 87, 114, 151, 203]
[203, 255, 322, 409, 523, 674, 877]

```

**先打印出来，我们按照以下步骤:**

*   我们在第一行写 1。
*   接下来，我们用前一行最右边的值填充每行最左边的值。
*   每行的下一个元素由简单的规则填充，即特定行的每个元素是该行左侧的值与同一位置的上一行的值的总和。
    为了更好的理解，让我们考虑由元素 2、3、5 组成的上述示例的第三行。该行最左边的值是上一行最右边的值，即 2。下一个值 3 是该行(2)左侧的值与上一行(1)相同位置的值之和。同样，5 是 3 和 2 的和。

下面是实现。

```py
# Python program to print
# Aitken's array

from queue import Queue
from functools import reduce, lru_cache

# for dynamic programming
# Recursive function to print the 
# Aitken's array.
@lru_cache()
def rec(n):

    # Base case
    if n == 1:
        print([1])
        return [1]

    array =  [rec(n-1)[-1]]

    for k in range(n-1):
        array.append(array[k] + rec(n-1)[k])

    print(array)

    return array

# Driver's code 
rec(7)
```

**输出:**

```py
[1]
[1, 2]
[2, 3, 5]
[5, 7, 10, 15]
[15, 20, 27, 37, 52]
[52, 67, 87, 114, 151, 203]
[203, 255, 322, 409, 523, 674, 877]

```