# Python |将嵌套列表拆分为两个列表

> 原文:[https://www . geesforgeks . org/python-split-nested-list-in-two-list/](https://www.geeksforgeeks.org/python-split-nested-list-into-two-lists/)

给定嵌套的 2D 列表，任务是将嵌套列表拆分为两个列表，使得第一个列表包含每个子列表的第一个元素，第二个列表包含每个子列表的第二个元素。

**方法一:使用`map, zip()`**

```
# Python code to demonstrate
# splitting nested list
# into 2 lists

# initialising nested lists
ini_list = [[1, 2], [4, 3], [45, 65], [223, 2]]

# printing initial lists
print ("initial list", str(ini_list))

# code to split it into 2 lists
res1, res2 = map(list, zip(*ini_list))

# printing result
print("final lists", res1, "\n", res2)
```

**输出:**

```
initial list [[1, 2], [4, 3], [45, 65], [223, 2]]
final lists [1, 4, 45, 223] 
 [2, 3, 65, 2]

```