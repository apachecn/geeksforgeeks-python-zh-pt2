# Python–元组矩阵列求和

> 原文:[https://www . geesforgeks . org/python-tuple-matrix-columns-summary/](https://www.geeksforgeeks.org/python-tuple-matrix-columns-summation/)

有时，在使用元组矩阵时，我们会遇到一个问题，即需要在元素级别对元组矩阵的每一列进行求和。这类问题可以在数据科学领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入**:test _ list =[(4，5)，(1，2)]，[(2，4)，(4，6)]
> **输出** : [(6，9)，(5，8)]
> 
> **输入**:test _ list =[(4，5)，(1，2)，(6，7)]
> **输出** : [(4，5)，(1，2)，(6，7)]

**方法#1:使用列表理解+ `zip() + sum()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 sum()执行 sum 任务，zip()用于执行所有元素的列式配对。

```
# Python3 code to demonstrate working of 
# Tuple Matrix Columns Summation
# Using list comprehension + zip() + sum()

# initializing lists
test_list = [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]

# printing original list
print("The original list is : " + str(test_list))

# Tuple Matrix Columns Summation
# Using list comprehension + zip() + sum()
res = [tuple(sum(ele) for ele in zip(*i)) for i in zip(*test_list)]

# printing result 
print("Tuple matrix columns summation : " + str(res))
```

**Output :**

```
The original list is : [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]
Tuple matrix columns summation : [(9, 9), (11, 13)]

```

**方法 2:使用`map() + list comprehension + zip()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 map()执行 sum()的扩展任务，其余功能的执行与上述方法类似。

```
# Python3 code to demonstrate working of 
# Tuple Matrix Columns Summation
# Using map() + list comprehension + zip()

# initializing lists
test_list = [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]

# printing original list
print("The original list is : " + str(test_list))

# Tuple Matrix Columns Summation
# Using map() + list comprehension + zip()
res = [tuple(map(sum, zip(*ele))) for ele in zip(*test_list)]

# printing result 
print("Tuple matrix columns summation : " + str(res))
```

**Output :**

```
The original list is : [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]
Tuple matrix columns summation : [(9, 9), (11, 13)]

```