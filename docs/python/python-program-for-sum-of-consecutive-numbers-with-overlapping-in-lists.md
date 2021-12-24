# 列表中重叠的连续数字总和的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-列表中有重叠的连续数字求和程序/](https://www.geeksforgeeks.org/python-program-for-sum-of-consecutive-numbers-with-overlapping-in-lists/)

给定一个列表，通过重叠对连续元素求和。

> **输入**:test _ list =【4，7，3，2】
> **输出**:【11，10，5，6】
> **解释** : 4 + 7 = 11，7 + 3 = 10，3 + 2 = 5，2 + 4 = 6。
> 
> **输入**:test _ list =【4，7，3】
> **输出**:【11，10，7】
> **解释** : 4+7=11，7+3=10，3+4=7。

**方法一:使用列表理解+ zip()**

在这种情况下，我们压缩列表，连续的元素使用[压缩()](https://www.geeksforgeeks.org/zip-in-python/)，然后使用+运算符进行求和。迭代部分使用[列表理解完成。](https://www.geeksforgeeks.org/comprehensions-in-python/)

## 蟒蛇 3

```
# initializing list
test_list = [4, 7, 3, 2, 9, 2, 1]

# printing original list
print("The original list is : " + str(test_list))

# using zip() to get pairing.
# last element is joined with first for pairing
res = [a + b for a, b in zip(test_list, test_list[1:] + [test_list[0]])]

# printing result
print("The Consecutive overlapping Summation : " + str(res))
```

**Output**

```
The original list is : [4, 7, 3, 2, 9, 2, 1]
The Consecutive overlapping Summation : [11, 10, 5, 11, 11, 3, 5]

```

**方法 2:使用 sum() +列表理解+ zip()**

在这种情况下，我们使用 sum()执行求和任务，并保持所有功能与上述方法相似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive overlapping Summation
# Using sum() + list comprehension + zip()

# initializing list
test_list = [4, 7, 3, 2, 9, 2, 1]

# printing original list
print("The original list is : " + str(test_list))

# using sum() to compute elements sum
# last element is joined with first for pairing
res = [sum(sub) for sub in zip(test_list, test_list[1:] + [test_list[0]])]  

# printing result 
print("The Consecutive overlapping Summation : " + str(res))
```

**Output**

```
The original list is : [4, 7, 3, 2, 9, 2, 1]
The Consecutive overlapping Summation : [11, 10, 5, 11, 11, 3, 5]

```