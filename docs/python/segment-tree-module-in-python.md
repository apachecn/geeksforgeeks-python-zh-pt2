# Python 中的段树模块

> 原文:[https://www . geesforgeks . org/segment-tree-module-in-python/](https://www.geeksforgeeks.org/segment-tree-module-in-python/)

**先决条件:** [段树实现](https://www.geeksforgeeks.org/segment-tree-set-1-sum-of-given-range/)
段树是一种数据结构，允许程序员有效地解决给定数组上的范围查询并修改数组值。基本上，Segment Tree 是一种非常灵活高效的数据结构，大量的问题都可以借助 Segment Tree 来解决。

**Python 段树模块**也用于解决范围查询问题。它在给定范围内执行各种操作，如**求和**、**最大**、**最小**、**T9】和**更新范围内的**值。该模块有助于避免分段树的实现，因为我们可以直接使用分段树函数来执行所有操作。
一般降低了实现段树的压力。**

**安装库:**

```
pip install segment-tree
```

#### 段树的功能:

*   **查询:**是段树的主要功能，执行在一个范围内查找**最大数**、在一个范围内查找**最小数**、查找给定范围的**和**等操作。它采用 3 个参数作为输入，它们是 start_index(即范围将从哪里开始)、End_index(即直到哪个索引范围结束)和要执行的操作。
    **语法:**

```
obj.query(Start_index, End_index, operation_name)
```

*   **更新:**段树的第二个主要功能是更新，它将**更新**范围内特定指标的值。它将用新值替换该索引中的现有值。
    **语法:**

```
obj.update(index, value)
```

**例 1:**

## 蟒蛇 3

```
from segment_tree import SegmentTree

# an array with some elements
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]

# here we are fitting our array
# into segment tree where t is
# taken as object of segment tree
# t will be used for performing
# operations on that segmentTree

t = SegmentTree(arr)

# here we are finding value
# of maximum number in a range
a = t.query(2, 9, "max")
print("The maximum value of this range is : ", a)

# here we are finding the value
# of minimum number in a range
a = t.query(2, 9, "min")
print("The minimum value of this range is : ", a)

# here we are finding the value
# of sum of a range
a = t.query(2, 7, "sum")
print("The sum of this range is : ", a)

# here we are updating the value
# of a particular index
t.update(2, 25)

# it will replace the value of
# index '2' with 25
print("The updated array is : ", arr)
```

**输出:**

```
The maximum value of this range is :  10
The minimum value of this range is :  3
The sum of this range is :  33
The updated array is :  [1, 2, 25, 4, 5, 6, 7, 8, 9, 10, 11]
```

**例 2:**

## 蟒蛇 3

```
from segment_tree import SegmentTree

# an array with some elements
arr = [14, 28, 55, 105, 78, 4, 24, 99, 48, 200]

# here we are fitting our array
# into segment tree where t is
# taken as object of segment tree
# t will be used for performing
# operations on that segmentTree

t = SegmentTree(arr)

# here we are finding value of
# maximum number in a range
a = t.query(0, 9, "max")
print("The maximum value of this range is : ", a)

# here we are finding value of
# minimum number in a range
a = t.query(0, 9, "min")
print("The minimum value of this range is : ", a)

# here we are finding value
# of sum of a range
a = t.query(0, 9, "sum")
print("The sum of this range is : ", a)

# here we are updating the value
# of a particular index
t.update(5, 0)
print("The updated array is : ", arr)

# here we are finding value of
# sum of a range
a = t.query(1, 5, "sum")
print("The sum of this range is : ", a)

# here we are updating the value
# of a particular index
t.update(4, 10)
print("The updated array is : ", arr)
```

**输出:**

```
The maximum value of this range is :  200
The minimum value of this range is :  4
The sum of this range is :  655
The updated array is :  [14, 28, 55, 105, 78, 0, 24, 99, 48, 200]
The sum of this range is :  266
The updated array is :  [14, 28, 55, 105, 10, 0, 24, 99, 48, 200]
```