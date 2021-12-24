# 在 Python 中对列表中的数字字符串进行排序

> 原文:[https://www . geesforgeks . org/python-sort-numeric-strings-in-a-list/](https://www.geeksforgeeks.org/python-sort-numeric-strings-in-a-list/)

排序列表是一项简单的任务，已经在许多情况下处理过了。随着机器学习和数据科学的出现，有时我们可以以数字列表的形式获得数据，但以字符串作为数据类型。在这种情况下，泛型排序函数会给出错误的结果，因此，必须采用其他几种方法来执行这个特定的任务。让我们讨论一下这是如何进行的。

**方法#1:天真方法**
在天真方法中需要将列表中的所有元素类型转换为整数通过循环迭代。之后，使用通用排序函数来执行任务。

```
# Python3 code to demonstrate 
# numeric string sorting
# using naive method 

# initializing list 
test_list = [ '4', '6', '7', '2', '1']

# printing original list 
print ("The original list is : " + str(test_list))

# using naive method 
# numeric string sorting
for i in range(0, len(test_list)) :
    test_list[i] = int(test_list[i])
test_list.sort()

# printing result
print ("The resultant sorted list  : " +  str(test_list))
```

**Output:**

```
The original list is : ['4', '6', '7', '2', '1']
The resultant sorted list  : [1, 2, 4, 6, 7]

```