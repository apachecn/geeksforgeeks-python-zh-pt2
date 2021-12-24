# Python–如果给定键的值为 N

，则移除字典

> 原文:[https://www . geesforgeks . org/python-remove-dictionary-if-given-key-value-is-n/](https://www.geeksforgeeks.org/python-remove-dictionary-if-given-keys-value-is-n/)

给定字典列表，删除关键字为 n 的字典

> **输入**:test _ list =[{“Gfg”:3、“is”:7、“Best”:8 }、{“Gfg”:9、“is”:2、“Best”:9 }、{“Gfg”:5、“is”:4、“Best”:10 }、{“Gfg”:3、“is”:6、“Best”:15 }]、K =“Gfg”、N = 9
> **输出**:[{“Gfg”:3、“is”:7、“Best”:8 }、{“Gfg”:5、“is”:4
> 
> **输入**:test _ list =[{“Gfg”:3、“is”:7、“Best”:8 }、{“Gfg”:9、“is”:2、“Best”:9 }、{“Gfg”:5、“is”:4、“Best”:10 }、{“Gfg”:3、“is”:6、“Best”:15 }]、K =“Best”、N = 10
> **输出**:[{“Gfg”:3、“is”:7、“Best”:8 }、{“Gfg”:9、“is”:2

**方法一:使用列表理解**

这是执行这项任务的方法之一。在本文中，我们使用条件检查提取和迭代，在一行中使用列表理解。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove Dictionaries whose Key(K) is N
# Using list comprehension

# initializing list
test_list = [{"Gfg" : 3, "is" : 7, "Best" : 8}, 
             {"Gfg" : 9, "is" : 2, "Best" : 9}, 
             {"Gfg" : 5, "is" : 4, "Best" : 10},
             {"Gfg" : 3, "is" : 6, "Best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "Gfg"

# initializing N 
N = 5

# returning only dictionaries with "Gfg" key not 5 
res = [sub for sub in test_list if sub[K] != N]

# printing result 
print("The extracted dictionaries : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3, 'is': 7, 'Best': 8}, {'Gfg': 9, 'is': 2, 'Best': 9}, {'Gfg': 5, 'is': 4, 'Best': 10}, {'Gfg': 3, 'is': 6, 'Best': 8}]
The extracted dictionaries : [{'Gfg': 3, 'is': 7, 'Best': 8}, {'Gfg': 9, 'is': 2, 'Best': 9}, {'Gfg': 3, 'is': 6, 'Best': 8}]

```

**方法 2:使用过滤器()+λ**

这是执行这项任务的另一种方式。在这种情况下，我们使用 filter()和 lambda 函数来检查 N 值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove Dictionaries whose Key(K) is N
# Using filter() + lambda

# initializing list
test_list = [{"Gfg" : 3, "is" : 7, "Best" : 8}, 
             {"Gfg" : 9, "is" : 2, "Best" : 9}, 
             {"Gfg" : 5, "is" : 4, "Best" : 10},
             {"Gfg" : 3, "is" : 6, "Best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "Gfg"

# initializing N 
N = 5

# Using filter() to check for N value
res = list(filter(lambda x: x[K] != N, test_list))

# printing result 
print("The extracted dictionaries : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3, 'is': 7, 'Best': 8}, {'Gfg': 9, 'is': 2, 'Best': 9}, {'Gfg': 5, 'is': 4, 'Best': 10}, {'Gfg': 3, 'is': 6, 'Best': 8}]
The extracted dictionaries : [{'Gfg': 3, 'is': 7, 'Best': 8}, {'Gfg': 9, 'is': 2, 'Best': 9}, {'Gfg': 3, 'is': 6, 'Best': 8}]

```