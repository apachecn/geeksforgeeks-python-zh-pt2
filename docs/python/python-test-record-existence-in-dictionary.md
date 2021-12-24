# Python–字典中存在测试记录

> 原文:[https://www . geesforgeks . org/python-test-record-in-dictionary/](https://www.geeksforgeeks.org/python-test-record-existence-in-dictionary/)

有时在处理记录池时，我们可能会遇到问题，需要检查某个键的特定值是否存在。这可以应用于许多领域，如日常编程或网络开发。让我们讨论执行这项任务的某些方法。
**方法#1:使用任意()+生成器表达式**
以上功能的组合可以用来执行此任务。在本文中，我们简单地使用 any()测试所有元素，并使用生成器表达式进行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test Record existence in Dictionary
# Using any() + generator expression

# initializing list
test_list = [{ 'name' : 'Nikhil', 'age' : 22},
             { 'name' : 'Akshat', 'age' : 23},
             { 'name' : 'Akash', 'age' : 23}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key and value
test_key = 'name'
test_val = 'Nikhil'

# Test Record existence in Dictionary
# Using any() + generator expression
res = any(sub[test_key] == test_val for sub in test_list)

# printing result
print("Does key value contain in dictionary list : " + str(res))
```

**Output : **

原始列表为:[{'name': 'Nikhil '，' age': 22}，{'name': 'Akshat '，' age': 23}，{'name': 'Akash '，' age': 23}]
字典列表中是否包含键值:True

**方法 2:使用 filter() + lambda**
以上功能的组合可以用来执行这个任务。在本文中，我们使用 filter 检查所有值，并使用 lambda 函数进行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test Record existence in Dictionary
# Using filter() + lambda

# initializing list
test_list = [{ 'name' : 'Nikhil', 'age' : 22},
             { 'name' : 'Akshat', 'age' : 23},
             { 'name' : 'Akash', 'age' : 23}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key and value
test_key = 'name'
test_val = 'Nikhil'

# Test Record existence in Dictionary
# Using filter() + lambda
res = filter(lambda sub: test_val in sub.values(), test_list)
if len(list(res)):
    res = True
else :
    res = False

# printing result
print("Does key value contain in dictionary list : " + str(res))
```

**Output : **

原始列表为:[{'name': 'Nikhil '，' age': 22}，{'name': 'Akshat '，' age': 23}，{'name': 'Akash '，' age': 23}]
字典列表中是否包含键值:True