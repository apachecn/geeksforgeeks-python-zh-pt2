# Python |将子列表中的每个元素乘以其索引

> 原文:[https://www . geeksforgeeks . org/python-将子列表中的每个元素乘以其索引/](https://www.geeksforgeeks.org/python-multiply-each-element-in-a-sublist-by-its-index/)

给定一个列表列表，任务是将子列表中的每个元素乘以其索引，并返回一个求和列表。

下面给出了几个解决问题的方法。

**方法#1:使用朴素方法**

```
# Python3 code to demonstrate
# to multiply numbers with position
# and add them to return num

import numpy as np

# initialising list
ini_list = [[3, 4, 7], [ 6, 7, 8], [ 10, 7, 5], [ 11, 12, 13]]

# printing initial_list
print ("initial_list ", ini_list)

res = []
# Using Naive Method
for sub_list in ini_list:
    sublistsum = 0

    for i, value in enumerate(sub_list):
        sublistsum = sublistsum + i * value

    res.append(sublistsum)

# printing result
print ("result", res)
```

**Output:**

```
initial_list  [[3, 4, 7], [6, 7, 8], [10, 7, 5], [11, 12, 13]]
result [18, 23, 17, 38]

```

**方法 2:使用列表理解**

```
# Python3 code to demonstrate
# to multiply numbers with position
# and add them to return num

# initialising list
ini_list = [[3, 4, 7], [ 6, 7, 8], [ 10, 7, 5], [ 11, 12, 13]]

# printing initial_list
print ("initial_list ", ini_list)

# Using list comprehension
res = [sum(i * j for i, j in enumerate(sublist)) 
                         for sublist in ini_list]

# printing result
print ("result", res)

```

**Output:**

```
initial_list  [[3, 4, 7], [6, 7, 8], [10, 7, 5], [11, 12, 13]]
result [18, 23, 17, 38]

```

**方法三:使用 numpy**

```
# Python3 code to demonstrate
# to multiply numbers with position
# and add them to return num

import numpy as np

# initialising list
ini_list = [[3, 4, 7], [ 6, 7, 8], [ 10, 7, 5], [ 11, 12, 13]]

# printing initial_list
print ("initial_list ", ini_list)

# Using numpy
res = [np.arange(len(sublist)).dot(sublist) for sublist in ini_list]

# printing result
print ("result", res)

```

**Output:**

```
initial_list  [[3, 4, 7], [6, 7, 8], [10, 7, 5], [11, 12, 13]]
result [18, 23, 17, 38]

```