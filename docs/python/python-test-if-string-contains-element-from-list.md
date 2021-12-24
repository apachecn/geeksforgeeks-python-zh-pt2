# Python |测试字符串是否包含列表

中的元素

> 原文:[https://www . geesforgeks . org/python-test-if-string-contains-element-from-list/](https://www.geeksforgeeks.org/python-test-if-string-contains-element-from-list/)

在 Python 的 web 开发过程中，我们通常会遇到一个问题，需要测试给定列表中的特定元素是否是子字符串。这种问题在机器学习领域也很常见。让我们讨论一下实现这一点的某些方法。
**方法#1:使用列表理解**
这个问题可以通过使用列表理解来解决，在这种情况下，我们检查列表并且还用字符串元素如果我们能找到匹配，并且返回 true，如果我们找到一个并且 false 则不使用条件语句。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# checking if string contains list element
# using list comprehension

# initializing string
test_string = "There are 2 apples for 4 persons"

# initializing test list
test_list = ['apples', 'oranges']

# printing original string
print("The original string : " + test_string)

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# checking if string contains list element
res = [ele for ele in test_list if(ele in test_string)]

# print result
print("Does string contain any list element : " + str(bool(res)))
```

**Output : **

```py
The original string : There are 2 apples for 4 persons
The original list : ['apples', 'oranges']
Does string contain any list element : True
```

**方法 2:使用任意()**
使用任意函数是执行这个任务最经典的方式，也是最高效的方式。该函数检查字符串是否与列表中的每个元素匹配。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# checking if string contains list element
# using list comprehension

# initializing string
test_string = "There are 2 apples for 4 persons"

# initializing test list
test_list = ['apples', 'oranges']

# printing original string
print("The original string : " + test_string)

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# checking if string contains list element
res = any(ele in test_string for ele in test_list)

# print result
print("Does string contain any list element : " + str(res))
```

**Output : **

```py
The original string : There are 2 apples for 4 persons
The original list : ['apples', 'oranges']
Does string contain any list element : True
```