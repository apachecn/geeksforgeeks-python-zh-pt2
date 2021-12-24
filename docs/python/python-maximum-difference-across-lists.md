# Python–列表间的最大差异

> 原文:[https://www . geesforgeks . org/python-跨列表最大差异/](https://www.geeksforgeeks.org/python-maximum-difference-across-lists/)

给定两个列表，任务是编写一个 Python 程序来找出相似索引元素之间的最大差异。

**示例:**

> **输入:** test_list1 = [3，4，2，1，7]，test_list2 = [6，2，1，9，1]
> 
> **输出:** 8
> 
> **说明:**9–1 = 8 是同一索引中列表之间的最大差异。
> 
> **输入:** test_list1 = [3，4，2，1，17]，test_list2 = [6，2，1，9，1]
> 
> **输出:** 16
> 
> **说明:**17–1 = 16 是同一索引中跨列表的最大差异。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**max()**](https://www.geeksforgeeks.org/max-min-python/)

在这种情况下，使用 abs()计算差异，并使用列表理解进行迭代。max()用于获取计算的子结果之间的最大差异的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum difference across lists
# Using list comprehension + max()

# initializing lists
test_list1 = [3, 4, 2, 1, 7]
test_list2 = [6, 2, 1, 9, 1]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# using max() to get maximum of extracted difference
res = max(abs(test_list2[idx] - test_list1[idx])
          for idx in range(0, len(test_list1) - 1))

# printing result
print("Maximum difference among lists : " + str(res))
```

**输出:**

```
The original list 1 is : [3, 4, 2, 1, 7]
The original list 2 is : [6, 2, 1, 9, 1]
Maximum difference among lists : 8
```

**方法二:使用**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)

在这种情况下，相似索引元素的配对是使用 zip()完成的。其余所有功能与上述方法类似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum difference across lists
# Using zip() + max()

# initializing lists
test_list1 = [3, 4, 2, 1, 7]
test_list2 = [6, 2, 1, 9, 1]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# using max() to get maximum of extracted difference
# zip() used to bind elements
res = max(abs(ele1 - ele2) for ele1, ele2 in zip(test_list1, test_list2))

# printing result
print("Maximum difference among lists : " + str(res))
```

**输出:**

```
The original list 1 is : [3, 4, 2, 1, 7]
The original list 2 is : [6, 2, 1, 9, 1]
Maximum difference among lists : 8
```