# Python–从集合中移除多个元素

> 原文:[https://www . geesforgeks . org/python-remove-multi-elements-from-set/](https://www.geeksforgeeks.org/python-remove-multiple-elements-from-set/)

给定一个集合，任务是编写一个 Python 程序从集合中移除多个元素。

**示例:**

```
Input : test_set = {6, 4, 2, 7, 9}, rem_ele = [2, 4, 8]
Output : {9, 6, 7}

Explanation : 2, 4 are removed from set.

Input : test_set = {6, 4, 2, 7, 9}, rem_ele = [4, 8]
Output : {2, 9, 6, 7}

Explanation : 4 is removed from set.
```

**方法#1:使用“-”运算符**

在这种情况下，我们使用“-”运算符执行使用计算差来消除元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove multiple elements from Set
# Using "-" operator

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing remove elements
rem_ele = [2, 4, 8]

# using "-" operator to remove multiple elements
res = test_set - set(rem_ele)

# printing result
print("Set after removal : " + str(res))
```

**输出:**

```
The original set is : {2, 4, 6, 7, 9}
Set after removal : {9, 6, 7}
```

**方法 2:使用 difference_update()**

在本文中，我们使用 inbuild set 方法 difference_update()移除获得差异的元素并更新集合。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove multiple elements from Set
# Using difference_update()

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing remove elements
rem_ele = [2, 4, 8]

# using difference_update() to remove multiple elements
test_set.difference_update(set(rem_ele))

# printing result
print("Set after removal : " + str(test_set))
```

**输出:**

```
The original set is : {2, 4, 6, 7, 9}
Set after removal : {9, 6, 7}
```