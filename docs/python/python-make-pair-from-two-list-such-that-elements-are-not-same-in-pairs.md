# Python |从两个列表中配对，使元素成对不相同

> 原文:[https://www . geeksforgeeks . org/python-从两个列表中制作成对元素成对不相同/](https://www.geeksforgeeks.org/python-make-pair-from-two-list-such-that-elements-are-not-same-in-pairs/)

给定两个列表，任务是从两个列表中创建成对的元素(成对可以重复)，使得成对的元素不相同。

**示例:**

```
Input : list1 = [100, 20, 30, 400]
        list2 = [400, 2, 30]
Output:
[[100, 400], [100, 2], [100, 30],
 [20, 400], [20, 2], [20, 30],
 [30, 400], [30, 2], [400, 2], [400, 30]]

Input: list1 = [10,20,30,40]
       list2 = [60, 10, 20]
Output:
[[10, 60], [10, 20], [20, 60], [20, 10],
 [30, 60], [30, 10], [30, 20],
 [40, 60], [40, 10], [40, 20]]

```

**方法一:使用列表理解**

```
# Python code to create pair of element 
# from two list such that element 
# in pairs are not equal.

# List initialization
list1 =[10, 20, 30, 40]
list2 =[40, 50, 60]

# using list comprehension
output = [[a, b] for a in list1 
          for b in list2 if a != b]

# printing output
print(output)
```

**Output:**

> [[10, 40], [10, 50], [10, 60], [20, 40], [20, 50], [20, 60], [30, 40], [30, 50], [30, 60], [40, 50], [40, 60]]

**方法 2:使用迭代工具和迭代**

```
# Python code to create pair of element 
# from two list such that element 
# in pairs are not equal.

# Importing
import itertools

# List initialization
list1 =[11, 22, 33, 44]
list2 =[22, 44, 66]

# using itertools
temp = list(itertools.product(list1, list1))

# output list initialization
out = []

# iteration
for elem in temp:
    if elem[0]!= elem[1]:
        out.append(elem)

# printing output
print(out)
```

**Output:**

> [(11, 22), (11, 33), (11, 44), (22, 11), (22, 33), (22, 44), (33, 11), (33, 22), (33, 44), (44, 11), (44, 22), (44, 33)]