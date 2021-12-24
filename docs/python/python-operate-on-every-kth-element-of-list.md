# Python |对列表的每一个 Kth 元素进行操作

> 原文:[https://www . geesforgeks . org/python-operate-on-ever-kth-element-of-list/](https://www.geeksforgeeks.org/python-operate-on-every-kth-element-of-list/)

我们通常希望对列表中的所有元素使用特定的函数。但是有时候，根据需求，我们希望对列表中的某些元素使用特定的功能，基本上是对列表中的每个 Kth 元素。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `enumerate()`**
获取列表每第 k 个数的功能可以借助列表理解来完成，枚举功能有助于整个列表的迭代。

```
# Python3 code to demonstrate
# Edit every Kth element in list 
# using list comprehension + enumerate()

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# using list comprehension + enumerate()
# Edit every Kth element in list 
# add 2 to every 3rd element
res = [i + 2 if j % 3 == 0 else i 
       for j, i in enumerate(test_list)]

# printing result
print ("The list after editing every kth element : " + str(res))
```

**Output:**

```
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The list after editing every kth element : [3, 4, 5, 8, 7, 8, 11, 12]

```

**方法 2:使用列表理解+列表切片**
上述功能可以帮助执行这些任务。列表理解完成列表中的迭代任务，列表切片完成每个 Kth 元素的提取。

```
# Python3 code to demonstrate
# Edit every Kth element in list 
# using list comprehension + list slicing 

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# using list comprehension + list slicing
# Edit every Kth element in list 
# add 2 to every 3rd element
test_list[0::3] = [i + 2 for i in test_list[0 :: 3]]

# printing result
print ("The list after editing every kth element : "
                                   + str(test_list))
```

**Output:**

```
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The list after editing every kth element : [3, 4, 5, 8, 7, 8, 11, 12]

```