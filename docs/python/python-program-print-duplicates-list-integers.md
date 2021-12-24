# Python |从整数列表中打印副本的程序

> 原文:[https://www . geesforgeks . org/python-program-print-duplicates-list-integers/](https://www.geeksforgeeks.org/python-program-print-duplicates-list-integers/)

给定一个包含重复元素的整数列表。生成另一个列表的任务，该列表只包含重复的元素。简单地说，新列表应该包含出现不止一个的元素。

**示例:**

```py
Input : list = [10, 20, 30, 20, 20, 30, 40, 50, -20, 60, 60, -20, -20]
Output : output_list = [20, 30, -20, 60]

Input :  list = [-1, 1, -1, 8]
Output : output_list = [-1]
```

**方法 1:** 使用蛮力方法

下面是实现:

## 蟒蛇 3

```py
# Python program to print
# duplicates from a list
# of integers
def Repeat(x):
    _size = len(x)
    repeated = []
    for i in range(_size):
        k = i + 1
        for j in range(k, _size):
            if x[i] == x[j] and x[i] not in repeated:
                repeated.append(x[i])
    return repeated

# Driver Code
list1 = [10, 20, 30, 20, 20, 30, 40,
         50, -20, 60, 60, -20, -20]
print (Repeat(list1))

# This code is contributed
# by Sandeep_anand
```

**输出:**

```py
[20, 30, -20, 60]
```

**方法 2:** 使用采集模块的 Counter()函数

## 蟒蛇 3

```py
from collections import Counter

l1 = [1,2,1,2,3,4,5,1,1,2,5,6,7,8,9,9]
d = Counter(l1)
print(d)

new_list = list([item for item in d if d[item]>1])
print(new_list)
```

**Output**

```py
Counter({1: 4, 2: 3, 5: 2, 9: 2, 3: 1, 4: 1, 6: 1, 7: 1, 8: 1})
[1, 2, 5, 9]
```