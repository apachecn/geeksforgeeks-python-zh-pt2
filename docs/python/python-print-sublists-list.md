# 在 Python 中打印列表的所有子列表

> 原文:[https://www.geeksforgeeks.org/python-print-sublists-list/](https://www.geeksforgeeks.org/python-print-sublists-list/)

给定一个列表，打印列表的所有子列表。

**示例:**

```
Input  : list = [1, 2, 3] 
Output : [[], [1], [1, 2], [1, 2, 3], [2], 
         [2, 3], [3]]

Input : [1, 2, 3, 4] 
Output : [[], [1], [1, 2], [1, 2, 3], [1, 2, 3, 4], 
         [2], [2, 3], [2, 3, 4], [3], [3, 4], [4]]
```

**进场:**

该方法将运行两个嵌套循环，直到给定列表的长度。外部循环 I 从 0 遍历到列表的长度，内部循环从 0 遍历到 I。需要在长度上增加 1，因为范围只从 0 遍历到 i-1。为了获得子阵列，我们可以使用切片来获得子阵列。

> 步骤 1:运行一个循环，直到给定列表的长度+1。
> 步骤 2:从 0 到 i.
> 运行另一个循环步骤 3:从 j 到 i.
> 对子阵列进行切片步骤 4:将其附加到另一个列表中进行存储
> 步骤 5:将其打印在最后

下面是上述方法的 Python 实现:

## 计算机编程语言

```
# Python program to print all
# sublist from a given list

# function to generate all the sub lists
def sub_lists (l):
    lists = [[]]
    for i in range(len(l) + 1):
        for j in range(i):
            lists.append(l[j: i])
    return lists

# driver code
l1 = [1, 2, 3]
print(sub_lists(l1))
```

**输出:**

```
[[], [1], [2], [1, 2], [3], [2, 3], [1, 2, 3]]
```