# Python–删除给定数字

之前的所有数字

> 原文:[https://www . geesforgeks . org/python-移除给定数字前的所有数字/](https://www.geeksforgeeks.org/python-remove-all-digits-before-given-number/)

给定一个字符串，去掉 K 数字前的所有数字。

**方法一:使用 split() + enumerate() + index() +列表理解**

这是执行这项任务的方法之一。在这种情况下，我们执行 split()任务来获取所有单词，使用 index()获取 K 个数字的索引，列表理解只能用于提取 K 个数字之后的数字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove digits before K Number
# Using split() + enumerate() + index() + list comprehension

# initializing string
test_str = 'geeksforgeeks 2 6 is 4 geeks 5 and CS8'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 4

# get K Number index
idx = test_str.split().index(str(K))

# isdigit() used to check for number 
res = [ele for i, ele in enumerate(test_str.split()) if not (i < idx and ele.isdigit())]
res = ' '.join(res)

# printing result 
print("String after removing digits before K : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks 2 6 is 4 geeks 5 and CS8
String after removing digits before K : geeksforgeeks is 4 geeks 5 and CS8

```

**方法 2:使用 regex() + index()**

在此方法中，regex 用于移除所需索引之前的所有元素，然后将字符串连接到索引前和索引后。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove digits before K Number
# Using regex() + index()
import re

# initializing string
test_str = 'geeksforgeeks 2 6 is 4 geeks 5 and CS8'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 4

# using regex to achieve task 
res = re.sub('[023456789]', '', test_str[0 : test_str.index(str(K))]) + test_str[test_str.index(str(K)):]

# printing result 
print("String after removing digits before K : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks 2 6 is 4 geeks 5 and CS8
String after removing digits before K : geeksforgeeks   is 4 geeks 5 and CS8

```