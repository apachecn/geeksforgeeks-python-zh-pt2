# Python |包含所有替代元素的列表

> 原文:[https://www . geesforgeks . org/python-list-由所有可选元素组成/](https://www.geeksforgeeks.org/python-list-consisting-of-all-the-alternate-elements/)

有些列表操作非常普通，不需要编写多行代码就能快速完成。想要构建由原始列表的所有替换元素组成的列表是一个开发人员在日常应用程序中面临的问题。

让我们讨论打印给定列表中所有可选元素的特定方法。

**方法一:使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)T3**

简单来说，列表理解提供了一种更快的方式来完成这个特殊的任务。在这种方法中，所有不是 2 的倍数(因此是奇数)的索引都被插入到新列表中。

```py
# Python code to demonstrate 
# to construct alternate element list
# using list comprehension 

# initializing list 
test_list = [1, 4, 6, 7, 9, 3, 5]

# printing original list 
print ("The original list : " + str(test_list))

# using list comprehension
# to construct alternate element list
res = [test_list[i] for i in range(len(test_list)) if i % 2 != 0]

# printing result 
print ("The alternate element list is : " + str(res))
```

**Output:**

```py
The original list : [1, 4, 6, 7, 9, 3, 5]
The alternate element list is : [4, 7, 3]

```

**方法 2:使用 `enumerate()`**
这只是列表理解方法的变体，但与列表理解具有相似的内部工作方式，但使用不同的变量来跟踪索引及其值。

```py
# Python code to demonstrate 
# to construct alternate element list
# using enumerate() 

# initializing list 
test_list = [1, 4, 6, 7, 9, 3, 5]

# printing original list 
print ("The original list : " + str(test_list))

# using enumerate()
# to construct alternate element list
res = [i for j, i in enumerate(test_list) if j % 2 != 0]

# printing result 
print ("The alternate element list is : " + str(res))
```

**Output:**

```py
The original list : [1, 4, 6, 7, 9, 3, 5]
The alternate element list is : [4, 7, 3]

```

**方法#3:使用切片符号**
这是执行这一特定任务的最富于蟒蛇性和优雅的方式，增强了蟒蛇的全部力量。我们可以使用 slice 提供的 skip 实用程序来获取列表中从头到尾的替换元素。

```py
# Python code to demonstrate 
# to construct alternate element list
# using Slice notation

# initializing list 
test_list = [1, 4, 6, 7, 9, 3, 5]

# printing original list 
print ("The original list : " + str(test_list))

# using Slice notation
# to construct alternate element list
res = test_list[1::2]

# printing result 
print ("The alternate element list is : " + str(res))
```

**Output:**

```py
The original list : [1, 4, 6, 7, 9, 3, 5]
The alternate element list is : [4, 7, 3]

```