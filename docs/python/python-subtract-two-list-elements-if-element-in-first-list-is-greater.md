# Python |如果第一个列表中的元素大于

，则减去两个列表元素

> 原文:[https://www . geesforgeks . org/python-减法-两个列表元素-如果第一个列表中的元素大于/](https://www.geeksforgeeks.org/python-subtract-two-list-elements-if-element-in-first-list-is-greater/)

给定两个列表，如果第一个列表中的元素大于第二个列表中的元素，则减去它，否则只返回第一个列表中的元素。
**例:**

```py
Input:
l1 = [10, 20, 30, 40, 50, 60]
l2 = [60, 50, 40, 30, 20, 10]
Output:
[10, 20, 30, 10, 30, 50]

Input:
l1 = [15, 9, 10, 56, 23, 78, 5, 4, 9]
l2 = [9, 4, 5, 36, 47, 26, 10, 45, 87]
Output:
[6, 5, 5, 20, 23, 52, 5, 4, 9]
```

**方法 1:** 最简单的方法是同时遍历两个列表，如果第一个列表中的元素大于第二个列表中的元素，则减去它，否则如果第一个列表中的元素小于第二个列表中的元素，则只返回第一个列表中的元素。

## 蟒蛇 3

```py
# Python code to subtract if element in first
# list is greater than element in second list,
# else we output element of first list.

# Input list initialisation
Input1 = [10, 20, 30, 40, 50, 60]
Input2 = [60, 50, 40, 30, 20, 10]

# Output list initialisation
Output = []

for i in range(len(Input1)):
    if Input1[i] > Input2[i]:
        Output.append(Input1[i] - Input2[i])
    else:
        Output.append(Input1[i])

print("Original list are :")
print(Input1)
print(Input2)

print("\nOutput list is")
print(Output)
```

**输出:**

```py
Original list are :
[10, 20, 30, 40, 50, 60]
[60, 50, 40, 30, 20, 10]

Output list is
[10, 20, 30, 10, 30, 50]
```

**方法 2:** 使用 zip()我们减去第一个列表中的元素是否大于第二个列表中的元素，否则我们输出第一个列表的元素。

## 蟒蛇 3

```py
# Python code to subtract if element in first
# list is greater than element in second list,
# else we output element of first list.

# Input list initialisation
Input1 = [10, 20, 30, 40, 50, 60]
Input2 = [60, 50, 40, 30, 20, 10]

# using zip()
Output =[e1-e2 if e1>e2 else e1 for (e1, e2) in zip(Input1, Input2)]

# Printing output
print("Original list are :")
print(Input1)
print(Input2)

print("\nOutput list is")
print(Output)
```

**输出:**

```py
Original list are :
[10, 20, 30, 40, 50, 60]
[60, 50, 40, 30, 20, 10]

Output list is
[10, 20, 30, 10, 30, 50]
```

**方法三:**利用列表理解。

## 蟒蛇 3

```py
# Python code to subtract if element in first
# list is greater than element in second list,
# else we output element of first list.

# Input list initialisation
Input1 = [10, 20, 30, 40, 50, 60]
Input2 = [60, 50, 40, 30, 20, 10]

# Output list initialisation
Output = [Input1[i]-Input2[i] if Input1[i] > Input2[i] \
          else Input1[i] for i in range(len(Input1))]

# Printing output
print("Original list are :")
print(Input1)
print(Input2)

print("\nOutput list is")
print(Output)
```

**输出:**

```py
Original list are :
[10, 20, 30, 40, 50, 60]
[60, 50, 40, 30, 20, 10]

Output list is
[10, 20, 30, 10, 30, 50]
```

**方法 4:** 使用 numpy()完成上述任务。

## 蟒蛇 3

```py
# Python code to subtract if element in first
# list is greater than element in second list,
# else we output element of first list.

import numpy as np

# Input list initialisation
Input1 = np.array([10, 20, 30, 40, 50, 60])
Input2 = np.array([60, 50, 40, 30, 20, 10])

# using numpy
Output = np.where(Input1 >= Input2, Input1 - Input2, Input1)

# Printing output
print("Original list are :")
print(Input1)
print(Input2)

print("\nOutput list is")
print(Output)
```

**输出:**

```py
Original list are :
[10 20 30 40 50 60]
[60 50 40 30 20 10]

Output list is
[10 20 30 10 30 50]
```