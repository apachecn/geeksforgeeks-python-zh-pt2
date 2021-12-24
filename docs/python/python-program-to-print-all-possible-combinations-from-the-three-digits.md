# Python 程序打印三位数字的所有可能组合

> 原文:[https://www . geesforgeks . org/python-程序-打印-所有可能的三位数组合/](https://www.geeksforgeeks.org/python-program-to-print-all-possible-combinations-from-the-three-digits/)

给定 3 个数字 a、b 和 c，任务是从这些数字中找出所有可能的组合。

**示例:**

```py
Input: [1, 2, 3]
Output:
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1

Input: [0, 9, 5]
Output:
0 9 5
0 5 9
9 0 5
9 5 0
5 0 9
5 9 0

```

**方法 1:** 蛮力或天真方法

最简单的方法是从 0 到 3 运行 3 个循环，如果索引不相等，则打印列表中的所有数字。

**示例:**

## 蟒蛇 3

```py
# Python program to print all
# the possible combinations

def comb(L):

    for i in range(3):
        for j in range(3):
            for k in range(3):

                # check if the indexes are not
                # same
                if (i!=j and j!=k and i!=k):
                    print(L[i], L[j], L[k])

# Driver Code
comb([1, 2, 3])
```

**输出:**

```py
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1

```

**方法 2:** 使用[迭代工具.置换()](https://www.geeksforgeeks.org/python-itertools-permutations/)

此方法将列表作为输入，并返回包含列表形式的所有置换的元组的对象列表。

**示例:**

## 蟒蛇 3

```py
# Python program to print all
# the possible combinations

from itertools import permutations

# Get all combination of [1, 2, 3]
# of length 3
comb = permutations([1, 2, 3], 3)

for i in comb:
    print(i)
```

**输出:**

```py
(1, 2, 3)
(1, 3, 2)
(2, 1, 3)
(2, 3, 1)
(3, 1, 2)
(3, 2, 1)

```