# Python 程序获取布尔列表中真值的索引

> 原文:[https://www . geesforgeks . org/python-program-to-fetch-the-indexs-of-true-values-in-a-boolean-list/](https://www.geeksforgeeks.org/python-program-to-fetch-the-indices-of-true-values-in-a-boolean-list/)

给定一个只有布尔值的列表，编写一个 Python 程序从给定的列表中获取所有具有真值的索引。

让我们看看完成这项任务的某些方法。

**方法#1:** 使用 ITER tools[python 方式]

`itertools.compress()`函数检查列表中的所有元素，并返回具有真值的索引列表。

```
# Python program to fetch the indices
# of true values in a Boolean list
from itertools import compress 

# initializing list  
bool_list = [False, True, False, True, True, True] 

# printing given list  
print ("Given list is : " +  str(bool_list)) 

# using itertools.compress() 
# to return true indices. 
res = list(compress(range(len(bool_list )), bool_list )) 

# printing result 
print ("Indices having True values are : " +  str(res)) 
```

**Output:**

```
Given list is : [False, True, False, True, True, True]
Indices having True values are : [1, 3, 4, 5]

```

**方法 2:** 使用`enumerate()`方法

`enumerate()`方法用其值散列索引，并结合列表理解可以让我们检查真实值。

```
# Python program to fetch the indices
# of true values in a Boolean list

# initializing list  
bool_list = [False, True, False, True, True, True] 

# printing given list  
print ("Given list is : " +  str(bool_list)) 

# using enumerate() + list comprehension 
# to return true indices. 
res = [i for i, val in enumerate(bool_list) if val] 

# printing result 
print ("Indices having True values are : " +  str(res)) 
```

**Output:**

```
Given list is : [False, True, False, True, True, True]
Indices having True values are : [1, 3, 4, 5]

```

**方法 3:** 使用`filter()` + `range()`

```
# Python program to fetch the indices
# of true values in a Boolean list

# initializing list  
bool_list = [False, True, False, True, True, True] 

# printing given list  
print ("Given list is : " +  str(bool_list)) 

# using lambda + filter() + range() 
# to return true indices. 
res = list(filter(lambda i: bool_list[i], range(len(bool_list)))) 

# printing result 
print ("Indices having True values are : " +  str(res)) 
```

**Output:**

```
Given list is : [False, True, False, True, True, True]
Indices having True values are : [1, 3, 4, 5]

```