# Python–记录元组列表中的最大值

> 原文:[https://www . geesforgeks . org/python-records-maxima-in-list-of-tuples/](https://www.geeksforgeeks.org/python-records-maxima-in-list-of-tuples/)

有时，在处理记录时，我们可能会遇到这样的问题:我们需要最大化元组列表容器的所有列。这种应用程序在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用 max() +列表理解+ zip()**
这个任务可以使用以上功能的组合来执行。在本文中，我们使用 zip()累积相似的索引元素，即列，然后使用列表理解迭代它们，并使用 max()执行最大化。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Records Maxima in List of Tuples
# using list comprehension + max() + zip()

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Records Maxima in List of Tuples
# using list comprehension + max() + zip()
res = [max(ele) for ele in zip(*test_list)]

# printing result
print("The Cumulative column maximum is : " + str(res))
```

**输出:**

```py
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cumulative column maximum is : [6, 7, 8]
```

**方法 2:使用 zip() + map() + max()**
此方法与上述方法类似。在这种情况下，由列表理解执行的任务由 map()执行，它将最大列数扩展到压缩元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Records Maxima in List of Tuples
# using zip() + map() + max()

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Records Maxima in List of Tuples
# using zip() + map() + max()
res = list(map(max, zip(*test_list)))

# printing result
print("The Cumulative column maximum is : " + str(res))
```

**输出:**

```py
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cumulative column maximum is : [6, 7, 8]
```