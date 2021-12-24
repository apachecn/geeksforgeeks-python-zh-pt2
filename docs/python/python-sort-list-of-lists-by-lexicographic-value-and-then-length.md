# Python |按字典值然后按长度对列表列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-list-list-by-dictionary-value-then-length/](https://www.geeksforgeeks.org/python-sort-list-of-lists-by-lexicographic-value-and-then-length/)

python 列表中多次讨论了不同类型的排序。还讨论了 python 列表的排序。但是有时候，我们有两个参数需要排序。第一个是*列表总和*，第二个是其*长度*。让我们讨论如何解决这类问题。

**方法一:两次使用`sort()`**
想到的第一种方法是通用的方式，即两次使用排序函数，首先基于值，然后基于列表的大小。

```py
# Python code to demonstrate
# sort list of lists by value and length
# using sort() twice 

# initializing list 
test_list = [[1, 4, 3, 2], [5, 4, 1], [1, 4, 6, 7]]

# printing the original list
print ("The original list is : " + str(test_list))

# using sort() twice 
# sort list of lists by value and length
test_list.sort()
test_list.sort(key = len)

# printing result
print ("The list after sorting by value and length " + str(test_list))
```

**Output:**

> 原列表为:[[1，4，3，2]，[5，4，1]，[1，4，6，7]]
> 按值和长度排序后的列表[[5，4，1]，[1，4，3，2]，[1，4，6，7]]