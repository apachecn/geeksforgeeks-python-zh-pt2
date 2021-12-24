# Python |列表元素中的可选填充

> 原文:[https://www . geesforgeks . org/python-可选-列表中填充-元素/](https://www.geeksforgeeks.org/python-optional-padding-in-list-elements/)

在现实问题中，我们有时需要根据达到最大字符数的条件填充列表元素。如果数字的长度小于任何字段的要求，则用 0 填充数字是 web 开发中 Web 表单中出现的基本问题之一。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
这个问题可以使用基本的列表理解很容易地解决，在列表理解中，如果每个元素的大小小于指定的大小，我们只需要使用字符串格式来执行可选的 0 填充。

```py
# Python3 code to demonstrate 
# to perform list element padding
# using list comprehension

# initializing list  
test_list = [3, 54, 4, 1, 10]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# to perform list element padding
res = ["%02d" %i for i in test_list]

# printing result 
print ("The list after element padding " +  str(res))
```

**Output:**

```py
The original list is : [3, 54, 4, 1, 10]
The list after element padding ['03', '54', '04', '01', '10']

```

**方法 2:使用`str.rjust()`**
python 中有一个函数专门做这个工作。`rjust()` 函数执行指定字符串大小的任务，并获取需要填充字符的字符。

```py
# Python3 code to demonstrate 
# to perform list element padding
# using str.rjust()

# initializing list  
test_list = [3, 54, 4, 1, 10]

# printing original list
print ("The original list is : " + str(test_list))

# using str.rjust()
# to perform list element padding
res = [str(i).rjust(2, '0') for i in test_list]

# printing result 
print ("The list after element padding " +  str(res))
```

**Output:**

```py
The original list is : [3, 54, 4, 1, 10]
The list after element padding ['03', '54', '04', '01', '10']

```