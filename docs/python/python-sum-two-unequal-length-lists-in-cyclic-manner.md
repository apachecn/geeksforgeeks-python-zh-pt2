# Python |循环求和两个不等长列表

> 原文:[https://www . geesforgeks . org/python-sum-two-不等长循环列表/](https://www.geeksforgeeks.org/python-sum-two-unequal-length-lists-in-cyclic-manner/)

给定两个不等长的列表，任务是添加两个列表的元素，以便当较小列表的元素结束时，以循环方式添加元素，直到较大列表的所有元素都被迭代。

让我们讨论一下完成这项任务的不同方法。

**方法#1:使用迭代器和 zip**

```
# Python code to add two different
# length lists in cyclic manner

# Importing
from itertools import cycle

# List initialization
list1 = [150, 177, 454, 126]
list2 = [9, 44, 2, 168, 66, 80, 123, 6, 180, 184]

# Using zip
output = [x + y for x, y in zip(cycle(list1), list2)]

# Printing output
print(output)
```

**Output:**

```
[159, 221, 456, 294, 216, 257, 577, 132, 330, 361]

```

**方法 2:使用迭代器和星图**

```
# Python code to add two different 
# length lists in cyclic manner

# Importing
from itertools import starmap, cycle
from operator import add

# List initialization
list1 = [150, 177, 454, 126]
list2 = [9, 44, 2, 168, 66, 80, 123, 6, 180, 184]

# Using starmap
output = list(starmap(add, zip(cycle(list1), list2)))

# Print output
print(output)
```

**Output:**

```
[159, 221, 456, 294, 216, 257, 577, 132, 330, 361]

```

**方法三:使用列表理解**

```
# Python code to add two different
# length lists in cyclic manner

# List initialization
list1 = [150, 177, 454, 126]
list2 = [9, 44, 2, 168, 66, 80, 123, 6, 180, 184]

# List comprehension
output = [list1[i % len(list1)]+list2[i]
             for i in range(len(list2))]

# Printing output
print(output)
```

**Output:**

```
[159, 221, 456, 294, 216, 257, 577, 132, 330, 361]

```