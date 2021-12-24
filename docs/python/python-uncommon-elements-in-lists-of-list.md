# Python |列表中的不常见元素

> 原文:[https://www . geesforgeks . org/python-列表中的不常见元素/](https://www.geeksforgeeks.org/python-uncommon-elements-in-lists-of-list/)

这篇特别的文章旨在完成寻找不常见的两个列表的任务，其中每个元素本身就是一个列表。这也是一个有用的工具，因为这种任务可以出现在程序员的生活中，如果他在开发世界中的话。让我们讨论一些完成这项任务的方法。

**方法 1:天真方法**
这是完成这个任务最简单的方法，使用蛮力方法执行一个循环，检查一个列表是否包含与另一个列表相似的列表，不包括那个列表。

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# Uncommon elements in List
# using naive method

# initializing lists
test_list1 = [ [1, 2], [3, 4], [5, 6] ]
test_list2 = [ [3, 4], [5, 7], [1, 2] ]

# printing both lists
print ("The original list 1 : " + str(test_list1))
print ("The original list 2 : " + str(test_list2))

# using naive method
# Uncommon elements in List
res_list = []
for i in test_list1:
    if i not in test_list2:
        res_list.append(i)
for i in test_list2:
    if i not in test_list1:
        res_list.append(i)

# printing the uncommon
print ("The uncommon of two lists is : " + str(res_list))
```

**Output : **

```py
The original list 1 : [[1, 2], [3, 4], [5, 6]]
The original list 2 : [[3, 4], [5, 7], [1, 2]]
The uncommon of two lists is : [[5, 6], [5, 7]]
```

**方法 2:使用 set() + map()和^**
执行此任务最有效和推荐的方法是使用 set()和 map()的组合来实现它。首先使用 map 将内部列表转换为元组，使用^算子将外部列表转换为集合，可以执行集合对称差，从而执行该任务。此外，如果需要以列表方式进入列表，我们可以使用 map()将外部和内部容器转换回列表。

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# Uncommon elements in Lists of List
# using map() + set() + ^

# initializing lists
test_list1 = [ [1, 2], [3, 4], [5, 6] ]
test_list2 = [ [3, 4], [5, 7], [1, 2] ]

# printing both lists
print ("The original list 1 : " + str(test_list1))
print ("The original list 2 : " + str(test_list2))

# using map() + set() + ^
# Uncommon elements in Lists of List
res_set = set(map(tuple, test_list1)) ^ set(map(tuple, test_list2))
res_list = list(map(list, res_set))

# printing the uncommon
print ("The uncommon of two lists is : " + str(res_list))
```

**Output : **

```py
The original list 1 : [[1, 2], [3, 4], [5, 6]]
The original list 2 : [[3, 4], [5, 7], [1, 2]]
The uncommon of two lists is : [[5, 6], [5, 7]]
```