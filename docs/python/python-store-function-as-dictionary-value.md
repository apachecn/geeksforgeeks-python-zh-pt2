# Python–将函数存储为字典值

> 原文:[https://www . geesforgeks . org/python-store-function-as-dictionary-value/](https://www.geeksforgeeks.org/python-store-function-as-dictionary-value/)

给定一个字典，将其键指定为函数调用。

**情况 1:无参数。**

实现这一任务的方法是，函数名作为字典值保存，用键调用时，添加括号“()”。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Functions as dictionary values
# Using Without params

# call Gfg fnc 
def print_key1():
    return "This is Gfg's value"

# initializing dictionary
# check for function name as key
test_dict = {"Gfg": print_key1, "is" : 5, "best" : 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# calling function using brackets 
res = test_dict['Gfg']()

# printing result 
print("The required call result : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': <function print_key1 at 0x7f1c0445be18>, 'is': 5, 'best': 9}
The required call result : This is Gfg's value

```

**情况 2:带参数**

用 params 调用的任务类似于上面的情况，在函数调用过程中，值像通常的函数调用一样在括号内传递。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Functions as dictionary values
# Using With params 

# call Gfg fnc 
def sum_key(a, b):
    return a + b

# initializing dictionary
# check for function name as key
test_dict = {"Gfg": sum_key, "is" : 5, "best" : 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# calling function using brackets 
# params inside brackets
res = test_dict['Gfg'](10, 34)

# printing result 
print("The required call result : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': <function sum_key at 0x7f538d017e18>, 'is': 5, 'best': 9}
The required call result : 44

```