# Python–math . dist()方法

> 原文:[https://www.geeksforgeeks.org/python-math-dist-method/](https://www.geeksforgeeks.org/python-math-dist-method/)

**Python 中的数学模块**包含许多数学运算，使用该模块可以轻松执行。Python 中的`***math.dist()***`方法用于计算两个点 p 和 q 之间的[欧几里德距离](https://en.wikipedia.org/wiki/Euclidean_distance)，每个点都作为坐标序列(或可迭代)给出。这两点必须具有相同的尺寸。
这个方法在 Python 版本中是新的。

> **语法:** math.dist(p，q)
> 
> **参数:**
> **p** :代表第一点的坐标序列或可重复序列
> **q** :代表第二点的坐标序列或可重复序列
> 
> **返回:**给定点之间的计算欧几里得距离。

**代码#1:** 使用`***math.dist()***`方法

```py
# Python Program to explain math.dist() method

# Importing math module
import math

# One dimensional Point

# Coordinate of Point P
P = 3

# Coordinates of point Q
Q = -8

# Calculate the Euclidean distance 
# between points P and Q
eDistance = math.dist([P], [Q])
print(eDistance)
```

**Output:**

```py
11.0

```

**代码#2:**

```py
# Python Program to explain math.dist() method

# Importing math module
import math

# Two dimensional Point

# Coordinates of Point P
Px = 3 
Py = 7

# Coordinates of point Q
Qx = -5
Qy = -9

# Calculate the Euclidean distance 
# between points P and Q
eDistance = math.dist([Px, Py], [Qx, Qy])
print(eDistance)

# Three-dimensional point

# Coordinates of Point P
P = [3, 6, 9]

# Coordinates of point Q
Q = [1, 0, -2] 

# Calculate the Euclidean distance 
# between points P and Q
eDistance = math.dist(P, Q)
print(eDistance)
```

**Output:**

```py
17.88854381999832
12.688577540449518

```

**代码#3:**

```py
# Python Program to explain math.dist() method

# Importing math module
import math

# n-dimensional Point

# Coordinates of Point P
P = [3, 9, 7, 2, 4, 5] 

# Coordinates of point Q
Q = [-5, -3, -9, 0, 6, 2]

# Calculate the Euclidean distance 
# between points P and Q
eDistance = math.dist(P, Q)
print(eDistance)

# Dimension of both points 
# should be the same 
```

**Output:**

```py
21.93171219946131

```

**参考:** [Python 数学库](https://docs.python.org/3/library/math.html#math.dist)