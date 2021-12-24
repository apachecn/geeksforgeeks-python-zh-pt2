# Python–将 K 乘以每第 n 个元素

> 原文:[https://www . geesforgeks . org/python-multiply-k-to-even n-element/](https://www.geeksforgeeks.org/python-multiply-k-to-every-nth-element/)

我们通常希望对列表中的所有元素使用特定的函数。但是有时，根据需求，我们希望对列表中的某些元素使用特定的功能，基本上是对列表中的每第 n 个元素。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `enumerate()`**
获取每第 n 个列表的功能可以借助列表理解来完成，枚举功能有助于整个列表的迭代。

```
# Python3 code to demonstrate
# Multiply K to every Nth element
# using list comprehension + enumerate()

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# initializing N
N = 3

# initializing K 
K = 2

# using list comprehension + enumerate()
# Multiply K to every Nth element
res = [i * K if j % N == 0 else i for j, i in enumerate(test_list)]

# printing result
print ("The list after multiplying K to every Nth element : " + str(res))
```

**Output :**

```
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The list after multiplying K to every Nth element : [2, 4, 5, 12, 7, 8, 18, 12]

```