# Python 集合运算(并集、交集、差集和对称差集)

> 原文:[https://www . geesforgeks . org/python-set-operations-union-交集-差分-对称-差分/](https://www.geeksforgeeks.org/python-set-operations-union-intersection-difference-symmetric-difference/)

本文演示了在 [Python 集合](https://www.geeksforgeeks.org/sets-in-python/)上的不同操作。
例子:

```
Input :
A = {0, 2, 4, 6, 8}
B = {1, 2, 3, 4, 5}

Output :
 Union : [0, 1, 2, 3, 4, 5, 6, 8]
 Intersection : [2, 4]
 Difference : [8, 0, 6]
 Symmetric difference : [0, 1, 3, 5, 6, 8]

```

在 Python 中，下面的快速操作数可以用于不同的操作。

> |代表工会。
> &为交点。
> –对于差异
> ^对于对称差异

```
# Program to perform different set operations
# as we do in  mathematics

# sets are define
A = {0, 2, 4, 6, 8};
B = {1, 2, 3, 4, 5};

# union
print("Union :", A | B)

# intersection
print("Intersection :", A & B)

# difference
print("Difference :", A - B)

# symmetric difference
print("Symmetric difference :", A ^ B)
```

**输出:**

```
('Union :', set([0, 1, 2, 3, 4, 5, 6, 8]))
('Intersection :', set([2, 4]))
('Difference :', set([8, 0, 6]))
('Symmetric difference :', set([0, 1, 3, 5, 6, 8]))

```