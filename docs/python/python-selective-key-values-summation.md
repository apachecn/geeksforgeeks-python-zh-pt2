# Python–选择性键值求和

> 原文:[https://www . geesforgeks . org/python-选择性-键值-求和/](https://www.geeksforgeeks.org/python-selective-key-values-summation/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们希望得到字典中某些键的值的总和。这种应用程序在许多领域都有用例，比如日常编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'Gfg' : 4，' is' : 2，' best' : 7}，key_list = ['Gfg '，' best']
> **输出** : 11
> 
> **输入** : test_dict = {'Gfg' : 4，' best' : 7}，key_list = ['Gfg']
> **输出** : 4

**方法#1:使用循环**
这是执行该任务的方法之一。在这种情况下，我们迭代目标列表键，并对字典中相应的值求和。

```
# Python3 code to demonstrate working of 
# Selective Key Values Summation
# Using loop

# initializing dictionary
test_dict = {'Gfg' : 4, 'is' : 2, 'best' : 7, 'for' : 9, 'geeks' : 10} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing keys_list
key_list = ['Gfg', 'best', 'geeks']

# Selective Key Values Summation
# Using loop
res = 0  
for key in key_list:
    res += test_dict[key]  

# printing result 
print("The keys summation : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'Gfg': 4, 'is': 2, 'best': 7, 'for': 9, 'geeks': 10}
The keys summation : 21

```

**方法二:使用`sum()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们使用 sum()执行求和，使用列表理解执行迭代任务。

```
# Python3 code to demonstrate working of 
# Selective Key Values Summation
# Using sum() + list comprehension

# initializing dictionary
test_dict = {'Gfg' : 4, 'is' : 2, 'best' : 7, 'for' : 9, 'geeks' : 10} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing keys_list
key_list = ['Gfg', 'best', 'geeks']

# Selective Key Values Summation
# Using sum() + list comprehension
res = sum([test_dict[key] for key in key_list])

# printing result 
print("The keys summation : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'Gfg': 4, 'is': 2, 'best': 7, 'for': 9, 'geeks': 10}
The keys summation : 21

```