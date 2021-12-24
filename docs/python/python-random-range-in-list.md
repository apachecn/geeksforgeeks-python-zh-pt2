# Python–列表中的随机范围

> 原文:[https://www.geeksforgeeks.org/python-random-range-in-list/](https://www.geeksforgeeks.org/python-random-range-in-list/)

给定一个列表，从中提取随机范围。

> **输入**:test _ list =【3，19，4，8，10，13，5，7，2，1，4】
> **输出**:【5，7，2，1】
> **解释**:随机范围元素提取任意长度。
> 
> **输入**:test _ list =【3，19，4，8，10，13，5，7，2，1，4】
> **输出**:【4，8】
> **解释**:随机范围元素提取任意长度。

**方法:使用 randrange() +切片**

[**rand range():**](https://www.geeksforgeeks.org/randrange-in-python/)**Python 提供了一个可以从指定范围生成随机数的功能，还允许包含房间的步骤，在*rand*模块中称为 *randrange()* 。**

**在这种情况下，我们提取列表的索引，对于第一个索引，然后再次使用函数从起始索引到列表长度使用 *randrange()* 来获取范围的结束部分。使用切片提取范围。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Random range in list
# Using randrange() + slicing
import random

# function to Random range in list
def rabdomRangeList(test_list):
    # getting ranges
    strt_idx = random.randrange(0, len(test_list) - 1)
    end_idx = random.randrange(strt_idx, len(test_list) - 1)

    # getting range elements
    res = test_list[strt_idx: end_idx]

    return str(res)

# Driver Code
# initializing list
input_list1 = [3, 19, 4, 8, 10, 13, 5, 7, 2, 1, 4]

# printing original list
print("\nThe original list is : ", input_list1)

# printing result
print("Required List : " + rabdomRangeList(input_list1))

# initializing list
input_list2 = [3, 19, 4, 8, 10, 13, 5, 7, 2, 1, 4]

# printing original list
print("\nThe original list is : ", input_list2)

# printing result
print("Required List : " + rabdomRangeList(input_list2))

# initializing list
input_list3 = [3, 19, 4, 8, 10, 13, 5, 7, 2, 1, 4]

# printing original list
print("\nThe original list is : ", input_list3)

# printing result
print("Required List : " + rabdomRangeList(input_list3))
```

****输出:****

```
The original list is :  [3, 19, 4, 8, 10, 13, 5, 7, 2, 1, 4]
Required List : [19]

The original list is :  [3, 19, 4, 8, 10, 13, 5, 7, 2, 1, 4]
Required List : [10, 13, 5, 7]

The original list is :  [3, 19, 4, 8, 10, 13, 5, 7, 2, 1, 4]
Required List : []
```