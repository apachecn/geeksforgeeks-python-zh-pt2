# Python–按元组关键字产品排序字典

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-tuple-key-product/](https://www.geeksforgeeks.org/python-sort-dictionary-by-tuple-key-product/)

给定带有元组关键字的字典，按关键字的元组乘积对字典项目进行排序。

> **输入** : test_dict = {(2，3) : 3，(6，3) : 9，(8，4): 10，(10，4): 12}
> **输出** : {(2，3) : 3，(6，3) : 9，(8，4): 10，(10，4): 12}
> **解释** : 6 < 18 < 32 < 40，重点产品因此保留订单。
> 
> **输入** : test_dict = {(20，3) : 3，(6，3) : 9，(8，4): 10，(10，4): 12}
> **输出** : {(6，3) : 9，(8，4): 10，(10，4): 12，(20，3) : 3，}
> **解释** : 18 < 32 < 40 < 60，重点产品因此调整订单。

**方法#1:使用词典理解+ lambda + sorted()**

这是执行这项任务的方法之一。在本文中，我们使用 sort()执行 sort()，lambda 函数用于计算可以执行排序的乘积。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort dictionary by Tuple Key Product
# Using dictionary comprehension + sorted() + lambda

# initializing dictionary
test_dict = {(5, 6) : 3, (2, 3) : 9, (8, 4): 10, (6, 4): 12}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sorted() over lambda computed product 
# dictionary comprehension reassigs dictionary by order 
res = {key: test_dict[key] for key in sorted(test_dict.keys(), key = lambda ele: ele[1] * ele[0])}

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {(5, 6): 3, (2, 3): 9, (8, 4): 10, (6, 4): 12}
The sorted dictionary : {(2, 3): 9, (6, 4): 12, (5, 6): 3, (8, 4): 10}

```

**方法 2:使用 dict() + sorted() + lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，使用与上述方法类似的方法。唯一的区别是在计算关键字排序后，使用 dict()而不是字典理解来完成项目排列。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort dictionary by Tuple Key Product
# Using dict() + sorted() + lambda

# initializing dictionary
test_dict = {(5, 6) : 3, (2, 3) : 9, (8, 4): 10, (6, 4): 12}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sorted() over lambda computed product 
# dict() used instead of dictionary comprehension for rearrangement
res = dict(sorted(test_dict.items(), key = lambda ele: ele[0][1] * ele[0][0]))

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {(5, 6): 3, (2, 3): 9, (8, 4): 10, (6, 4): 12}
The sorted dictionary : {(2, 3): 9, (6, 4): 12, (5, 6): 3, (8, 4): 10}

```