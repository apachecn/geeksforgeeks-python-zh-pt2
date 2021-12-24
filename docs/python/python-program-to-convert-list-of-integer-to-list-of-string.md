# Python 程序将整数列表转换为字符串列表

> 原文:[https://www . geesforgeks . org/python-程序-转换-整数列表-字符串列表/](https://www.geeksforgeeks.org/python-program-to-convert-list-of-integer-to-list-of-string/)

给定一个整数列表。任务是将它们转换为字符串列表。

**示例:**

```py
Input: [1, 12, 15, 21, 131]
Output: ['1', '12', '15', '21', '131']

Input: [0, 1, 11, 15, 58]
Output: ['0', '1', '11', '15', '58']

```

**方法 1:** 使用`map()`

```py
# Python code to convert list of 
# string into sorted list of integer 

# List initialization 
list_int = [1, 12, 15, 21, 131]

# mapping 
list_string = map(str, list_int) 

# Printing sorted list of integers 
print(list(list_string))
```

**输出:**

```py
['1', '12', '15', '21', '131']

```

**示例 2:** 使用列表理解

```py
# Python code to convert list of  
# string into sorted list of integer 

# List initialization 
list_string = [1, 12, 15, 21, 131]

# Using list comprehension 
output = [str(x) for x in list_string]

# Printing output 
print(output)
```

**输出:**

```py
['1', '12', '15', '21', '131']

```

**方法 3:** 使用迭代

```py
# Python code to convert list of 
# string into sorted list of integer 

# List initialization 
list_string = [1, 12, 15, 21, 131]

list_int = []
# using iteration and sorted() 
for i in list_string:
    list_int.append(i)

# printing output 
print(list_int) 
```

**输出:**

```py
['1', '12', '15', '21', '131']

```