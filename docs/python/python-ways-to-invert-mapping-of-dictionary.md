# Python |字典的反向映射方式

> 原文:[https://www . geeksforgeeks . org/python-字典的反向映射方式/](https://www.geeksforgeeks.org/python-ways-to-invert-mapping-of-dictionary/)

[字典](https://www.geeksforgeeks.org/python-dictionary/)是一个无序的、可变的、有索引的集合。在 Python 中，字典是用花括号写的，它们有键和值。它广泛用于日常编程、web 开发和机器学习。
让我们讨论几个方法来反转字典的映射。
**方法 1:** 使用字典理解。

```
# Python code to demonstrate
# how to invert mapping 
# using dict comprehension

# initialising dictionary
ini_dict = {101: "akshat", 201 : "ball"}

# print initial dictionary
print("initial dictionary : ", str(ini_dict))

# inverse mapping using dict comprehension
inv_dict = {v: k for k, v in ini_dict.items()}

# print final dictionary
print("inverse mapped dictionary : ", str(inv_dict))
```

**Output:**

```
initial dictionary :  {201: 'ball', 101: 'akshat'}
inverse mapped dictionary :  {'ball': 201, 'akshat': 101}

```

**方法 2:** 使用`dict.keys()`和`dict.values()`

```
# Python code to demonstrate
# how to invert mapping 
# using zip and dict functions

# initialising dictionary
ini_dict = {101: "akshat", 201 : "ball"}

# print initial dictionary
print("initial dictionary : ", str(ini_dict))

# inverse mapping using zip and dict functions
inv_dict = dict(zip(ini_dict.values(), ini_dict.keys()))

# print final dictionary
print("inverse mapped dictionary : ", str(inv_dict))
```

**Output:**

```
initial dictionary :  {201: 'ball', 101: 'akshat'}
inverse mapped dictionary :  {'ball': 201, 'akshat': 101}

```

**方法 3:** 使用 `map()`并反转

```
# Python code to demonstrate
# how to invert mapping 
# using map and reversed

# initialising dictionary
ini_dict = {101: "akshat", 201 : "ball"}

# print initial dictionary
print("initial dictionary : ", str(ini_dict))

# inverse mapping using map and reversed
inv_dict = dict(map(reversed, ini_dict.items()))

# print final dictionary
print("inverse mapped dictionary : ", str(inv_dict))
```

**Output:**

```
initial dictionary :  {201: 'ball', 101: 'akshat'}
inverse mapped dictionary :  {'akshat': 101, 'ball': 201}

```

**方法#4:** 使用λ

```
# Python code to demonstrate
# how to invert mapping 
# using lambda

# initialising dictionary
ini_dict = {101 : "akshat", 201 : "ball"}

# print initial dictionary
print("initial dictionary : ", str(ini_dict))

# inverse mapping using lambda
lambda ini_dict: {v:k for k, v in ini_dict.items()}

# print final dictionary
print("inverse mapped dictionary : ", str(ini_dict))
```

**Output:**

```
initial dictionary :  {201: 'ball', 101: 'akshat'}
inverse mapped dictionary :  {201: 'ball', 101: 'akshat'}

```