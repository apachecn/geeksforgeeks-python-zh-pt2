# Python |将字符串拆分为字符列表

> 原文:[https://www . geesforgeks . org/python-拆分-字符串到字符列表/](https://www.geeksforgeeks.org/python-splitting-string-to-list-of-characters/)

有时我们只需要处理列表，因此字符串可能需要转换成列表。对于要执行的某些任务，它必须转换为字符列表。这通常是机器学习中预处理数据和文本分类所必需的。

让我们讨论执行这项任务的某些方式。

**方法#1:使用列表切片**
列表切片可以用于此特定目的，其中我们使用切片操作为列表的每个索引元素分配字符串的下一个出现的字符。

```py
# Python3 code to demonstrate 
# splitting string to list of characters.
# using list slicing

# initializing string
test_string = "GeeksforGeeks"

# printing original string 
print ("The original string is : " + str(test_string))

# using list slicing
# for splitting string to list of characters
res = []
res[:] = test_string

# printing result
print ("The resultant list of characters : " +  str(res))
```

**Output:**

> 原始字符串是:GeeksforGeeks
> 结果字符列表:['G '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' G '，' e '，' e '，' k '，' s']

**方法二:使用`list()`**
最简洁易读的拆分方式是将案例串键入列表，列表的拆分在内部自动处理。这是执行此特定任务的推荐方法。

```py
# Python3 code to demonstrate 
# splitting string to list of characters.
# using list()

# initializing string
test_string = "GeeksforGeeks"

# printing original string 
print ("The original string is : " + str(test_string))

# using list()
# for splitting string to list of characters
res = list(test_string)

# printing result
print ("The resultant list of characters : " +  str(res))
```

**Output:**

> 原始字符串是:GeeksforGeeks
> 结果字符列表:['G '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' G '，' e '，' e '，' k '，' s']

**方法 3:使用`map() + lambda`**
这是执行这个特殊任务的另一种方式。虽然不推荐，但可以在某些情况下使用。但缺点是牺牲了代码的可读性。

```py
# Python3 code to demonstrate 
# splitting string to list of characters.
# using map() + lambda

# initializing string
test_string = "GeeksforGeeks"

# printing original string 
print ("The original string is : " + str(test_string))

# using map() + lambda
# for splitting string to list of characters
res = list(map(lambda i:i, test_string))

# printing result
print ("The resultant list of characters : " +  str(res))
```

**Output:**

> 原始字符串是:GeeksforGeeks
> 结果字符列表:['G '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' G '，' e '，' e '，' k '，' s']