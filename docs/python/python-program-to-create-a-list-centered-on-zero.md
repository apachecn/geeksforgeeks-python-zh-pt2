# Python 程序创建以零为中心的列表

> 原文:[https://www . geesforgeks . org/python-program-to-create-list-以零为中心/](https://www.geeksforgeeks.org/python-program-to-create-a-list-centered-on-zero/)

给定两个整数变量，*极限*和 *diff* ，编写 Python 程序创建一个以零为中心的列表，使用*极限*指定列表的极限，使用 *diff* 指定整数之间的公共差。

**示例:**

```py
Input : limit = 1, diff = 0.5
Output : [-1, -0.5, 0.0, 0.5, 1]

Input : limit = 25, diff = 5
Output : [-25, -20, -15, -10, -5, 0, 5, 10, 15, 20, 25]

```

**方法#1 :** 简单方法

这是解决上述问题的一种幼稚的方法。首先，创建一个空列表“lst”，然后我们使用 while 循环来附加下一个差值等于“diff”的整数。

```py
# Python3 program to Convert a 
# list to dictionary

def create(limit, diff):

    lst = [-limit]
    while lst[-1] < limit:
        lst.append(lst[-1] + diff)
    lst[-1] = limit
    return lst

# Driver code
limit = 1
diff = 0.5
print(create(limit, diff))
```

**Output:**

```py
[-1, -0.5, 0.0, 0.5, 1]

```

**方法 2 :** 使用 Python Numpy

使用 Numpy 模块使解决方案变得更加容易。在这种方法中，我们使用`np.arange`，它在给定的间隔‘diff’内返回均匀间隔的值。

```py
# Python3 program to Convert a 
# list to dictionary
import numpy as np

def create(limit, diff):
    lst = np.arange(diff, limit, diff)
    if (lst[-1] != limit):
        lst = np.r_[lst, limit]

    return np.r_[-lst[::-1], 0, lst].tolist()

# Driver code
limit = 1
diff = 0.5
print(create(limit, diff))
```

**Output:**

```py
[-1.0, -0.5, 0.0, 0.5, 1.0]

```

**进场#3 :** [列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

```py
# Python3 Python program to create a list centered on zero

def create(limit, diff):
    length = int(((limit/diff)*2)+1)    
    list = [-limit+i*diff for i in range(length)]
    return list  

# Driver code
limit = 1
diff = 0.5
print(create(limit, diff))
```

**Output:**

```py
[-1.0, -0.5, 0.0, 0.5, 1.0]

```