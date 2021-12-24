# Python |从值中搜索关键字

> 原文:[https://www.geeksforgeeks.org/python-search-key-from-value/](https://www.geeksforgeeks.org/python-search-key-from-value/)

从给定的键中找到一个值是很常见的问题。但是我们可能有一个问题，我们希望从我们输入的输入键中获得返回键。让我们讨论一下解决这个问题的某些方法。
**方法#1:使用天真方法**
在这个方法中，我们只需为每个值运行一个循环，并返回其值匹配的相应的一个或多个键。这是执行这一特殊任务的暴力方式。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Search Key from Value
# Using naive method

# initializing dictionary
test_dict = {'Gfg' : 1, 'for' : 2, 'CS' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing value
val = 3

# Using naive method
# Search key from Value
for key in test_dict:
    if test_dict[key] == val:
        res = key

# printing result
print("The key corresponding to value : " + str(res))
```

**Output**

```py
The original dictionary is : {'Gfg': 1, 'for': 2, 'CS': 3}
The key corresponding to value : CS

```

**方法 2:使用 items() +列表理解**
使用 items()可以很容易地解决这个问题，items()用于同时提取键和值，因此使搜索变得容易，并且可以使用列表理解来执行，使其成为一个线性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Search Key from Value
# Using items() + list comprehension

# initializing dictionary
test_dict = {'Gfg' : 1, 'for' : 2, 'CS' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing value
val = 3

# Using items() + list comprehension
# Search key from Value
res = [key for key, value in test_dict.items() if value == val]

# printing result
print("The key corresponding to value : " + str(res))
```

**Output**

```py
The original dictionary is : {'Gfg': 1, 'for': 2, 'CS': 3}
The key corresponding to value : ['CS']

```