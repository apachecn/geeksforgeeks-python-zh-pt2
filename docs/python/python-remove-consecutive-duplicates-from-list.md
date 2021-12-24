# Python |从列表中删除连续的重复项

> 原文:[https://www . geesforgeks . org/python-从列表中删除连续重复项/](https://www.geeksforgeeks.org/python-remove-consecutive-duplicates-from-list/)

在 Python 中，我们通常希望移除重复的元素，但是有时对于几个特定的用例，我们要求仅移除连续重复的元素。这是一项相当简单的任务，有一个简写可能会很有用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`groupby()` +列表理解**
使用 groupby 函数，我们可以将一起出现的元素分组为一个，并可以连续移除所有重复的元素，只让一个元素在列表中。

```
# Python3 code to demonstrate 
# removing consecutive duplicates
# using groupby() + list comprehension
from itertools import groupby 

# initializing list
test_list = [1, 4, 4, 4, 5, 6, 7, 4, 3, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using groupby() + list comprehension
# removing consecutive duplicates 
res = [i[0] for i in groupby(test_list)]

# printing result 
print ("The list after removing consecutive duplicates : " +  str(res))
```

**Output:**

```
The original list is : [1, 4, 4, 4, 5, 6, 7, 4, 3, 3, 9]
The list after removing consecutive duplicates : [1, 4, 5, 6, 7, 4, 3, 9]

```

**方法二:使用`zip_longest()` +列表理解**
这个功能可以使用切片的方式来保留元素，删除后续的元素。zip _ longest 函数的任务是将一个列表中的值集合在一起。

```
# Python3 code to demonstrate 
# removing consecutive duplicates
# using zip_longest()+ list comprehension
from itertools import zip_longest

# initializing list
test_list = [1, 4, 4, 4, 5, 6, 7, 4, 3, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using zip_longest()+ list comprehension
# removing consecutive duplicates 
res = [i for i, j in zip_longest(test_list, test_list[1:])
                                                if i != j]

# printing result 
print ("List after removing consecutive duplicates : " +  str(res))
```

**Output:**

```
The original list is : [1, 4, 4, 4, 5, 6, 7, 4, 3, 3, 9]
List after removing consecutive duplicates : [1, 4, 5, 6, 7, 4, 3, 9]

```