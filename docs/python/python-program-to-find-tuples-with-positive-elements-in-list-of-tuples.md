# 在元组列表

中查找正元素元组的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序查找元组列表中具有正元素的元组/](https://www.geeksforgeeks.org/python-program-to-find-tuples-with-positive-elements-in-list-of-tuples/)

给定元组列表。任务是得到所有正元素的元组。

**示例:**

> **输入** : test_list = [(4，5，9)，(-3，2，3)，(-3，5，6)，(4，-6)]
> **输出** : [(4，5，9)]
> **解释**:提取出所有正元素的元组。
> 
> **输入** : test_list = [(-4，5，9)、(-3，2，3)、(-3，5，6)、(4，-6)]
> **输出** : []
> **解释**:没有包含所有正元素的元组。

**方法一:使用列表理解+ all()**

在这种情况下， [all()](https://www.geeksforgeeks.org/any-all-in-python/) 用于检查所有元组，列表理解有助于元组的迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Positive Tuples in List
# Using list comprehension + all()

# initializing list
test_list = [(4, 5, 9), (-3, 2, 3), (-3, 5, 6), (4, 6)]

# printing original list
print("The original list is : " + str(test_list))

# all() to check each element
res = [sub for sub in test_list if all(ele >= 0 for ele in sub)]

# printing result
print("Positive elements Tuples : " + str(res))
```

**Output**

> 原列表为:[(4，5，9)，(-3，2，3)，(-3，5，6)，(4，6)]
> 正元素元组:[(4，5，9)，(4，6)]

**方法 2:使用滤镜()+ lambda + all()**

在这种情况下，使用[滤波器()](https://www.geeksforgeeks.org/filter-in-python/)和[λ](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)功能执行滤波任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Positive Tuples in List
# Using filter() + lambda + all()

# initializing list
test_list = [(4, 5, 9), (-3, 2, 3), (-3, 5, 6), (4, 6)]

# printing original list
print("The original list is : " + str(test_list))

# all() to check each element
res = list(filter(lambda sub: all(ele >= 0 for ele in sub), test_list))

# printing result
print("Positive elements Tuples : " + str(res))
```

**Output**

> 原列表为:[(4，5，9)，(-3，2，3)，(-3，5，6)，(4，6)]
> 正元素元组:[(4，5，9)，(4，6)]