# Python |列表中大于 K 的数值个数

> 原文:[https://www . geesforgeks . org/python-值数-列表中大于 k/](https://www.geeksforgeeks.org/python-number-of-values-greater-than-k-in-list/)

其中一个问题基本上是许多复杂问题的子问题，即在 python 的列表中查找大于某个数字的数字，这是经常遇到的问题，本文将讨论这个特定问题的可能解决方案。

**方法 1:天真的方法**
解决这个问题最常见的方法是使用循环，只计算大于给定数字 k 的元素的出现次数

```
# Python 3 code to demonstrate 
# find number of elements > k
# using naive method 

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using naive method 
# to get numbers > k
count = 0
for i in test_list :
    if i > k :
        count = count + 1

# printing the intersection 
print ("The numbers greater than 4 : " + str(count))
```

**输出:**

```
The list : [1, 7, 5, 6, 3, 8]
The numbers greater than 4 : 4

```

**方法二:使用列表理解**
这个方法以类似的方式完成这个任务，但是方式更加简洁。列表理解总是降低程序中的代码行，即使在后台运行类似的方法。

```
# Python 3 code to demonstrate 
# find number of elements > k
# using list comprehension

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using list comprehension
# to get numbers > k
count = len([i for i in test_list if i > k])

# printing the intersection 
print ("The numbers greater than 4 : " + str(count))
```

**输出:**

```
The list : [1, 7, 5, 6, 3, 8]
The numbers greater than 4 : 4

```

**方法三:使用`sum()`**
`sum()`也可以帮助我们完成这个任务。当找到大于 k 的数时，我们可以返回 1，然后使用`sum()`
计算的和

```
# Python 3 code to demonstrate 
# find number of elements > k
# using sum()

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using sum()
# to get numbers > k
count = sum(i > k for i in test_list)

# printing the intersection 
print ("The numbers greater than 4 : " + str(count))
```

**输出:**

```
The list : [1, 7, 5, 6, 3, 8]
The numbers greater than 4 : 4

```

**方法 4:使用`functools.reduce()`**
通过使用`reduce()`，我们还可以对该函数收集的所有数字进行求和，然后对它们进行累加以返回结果，即大于 k 的数字的计数

```
# Python 3 code to demonstrate 
# find number of elements > k
# using reduce()
from functools import reduce

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using reduce()
# to get numbers > k
count = reduce(lambda sum, j: sum  + (1 if j > k else 0), test_list, 0)

# printing the intersection 
print ("The numbers greater than 4 : " + str(count))
```

**输出:**

```
The list : [1, 7, 5, 6, 3, 8]
The numbers greater than 4 : 4

```

**方法 5:使用`bisect() + sort()`**
`sort()`和`bisect()`的组合，实际上可以执行二分搜索法的任务，因此得到索引并减去列表的大小实际上可以帮助我们得到大于列表中特定元素的元素。

```
# Python 3 code to demonstrate 
# find number of elements > k
# using bisect() + sort()
from bisect import bisect

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using bisect() + sort()
# to get numbers > k
test_list.sort()
count = len(test_list) - bisect(test_list, k)

# printing the intersection 
print ("The numbers greater than 4 : " + str(count))
```

**输出:**

```
The list : [1, 7, 5, 6, 3, 8]
The numbers greater than 4 : 4

```