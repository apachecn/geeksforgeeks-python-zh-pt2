# Python–被列表中最大的邻居取代

> 原文:[https://www . geesforgeks . org/python-被列表中最伟大的邻居取代/](https://www.geeksforgeeks.org/python-replacing-by-greatest-neighbour-in-list/)

给定一个列表，任务是编写一个 Python 程序来替换前一个和下一个元素中最大的邻居。

> **输入** : test_list = [5，4，2，5，8，2，1，9]，
> **输出** : [5，5，5，8，8，8，9，9]
> **解释** : 4 是以 5 和 2 为邻居，替换为大于 2 的 5。
> 
> **输入** : test_list = [5，4，2，5]，
> **输出** : [5，5，5，5]
> **解释** : 4 是以 5 和 2 为邻，替换为大于 2 的 5。

**方法 1 :** 使用循环+链条件语句

在这种情况下，我们使用循环遍历列表中的所有元素，并使用条件检查邻居是否有更大的元素，然后被替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Replacing by Greatest Neighbour
# Using loop + chain conditional statements

# initializing list
test_list = [5, 4, 2, 5, 8, 2, 1, 9]

# printing original list
print("The original list is : " + str(test_list))

for idx in range(1, len(test_list) - 1):

    # replacing by greater Neighbour
    test_list[idx] = test_list[idx - 1] \
    if test_list[idx - 1] > test_list[idx + 1] \
    else test_list[idx + 1]

# printing result
print("The elements after replacing : " + str(test_list))
```

**输出:**

```
The original list is : [5, 4, 2, 5, 8, 2, 1, 9]
The elements after replacing : [5, 5, 5, 8, 8, 8, 9, 9]
```

**方法二:**使用 [max()](https://www.geeksforgeeks.org/python-max-function/) +循环。

在本文中，我们使用 max()得到相邻元素中的最大元素。循环用于迭代元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replacing by Greatest Neighbour
# Using max() + loop

# initializing list
test_list = [5, 4, 2, 5, 8, 2, 1, 9]

# printing original list
print("The original list is : " + str(test_list))

for idx in range(1, len(test_list) - 1):

    # using max() to get maximum of Neighbours
    test_list[idx] = max(test_list[idx - 1], test_list[idx + 1])

# printing result 
print("The elements after replacing : " + str(test_list))
```

**输出:**

```
The original list is : [5, 4, 2, 5, 8, 2, 1, 9]
The elements after replacing : [5, 5, 5, 8, 8, 8, 9, 9]
```