# Python–保留列表元素值项

> 原文:[https://www . geesforgeks . org/python-retain-list-elements-value-items/](https://www.geeksforgeeks.org/python-retain-list-elements-value-items/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们只需要保留那些键，它们的值是目标列表的一部分。这种问题在许多领域都有潜在的问题，包括 web 开发。让我们讨论执行这项任务的某些方法。

> **输入**:
> test _ dict = { ' gfg ':3 }
> tar _ list =[3，4，10](保留值)
> T5】输出 : {'gfg': 3}
> 
> **输入** :
> test_dict = {'gfg': 5，' best': 12}
> tar_list = [3，4，10](保留值)
> **输出** : {}

**方法一:利用字典理解**
这是解决这个问题的方法之一。在这种情况下，我们使用理解中的条件表达式执行过滤任务，只保留列表中的那些项目。

```
# Python3 code to demonstrate working of 
# Retain list elements value items
# Using dictionary comprehension

# initializing dictionary
test_dict = {'gfg': 3, 'is': 2, 'best': 4, 'for': 7, 'geeks': 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing target list 
tar_list = [3, 4, 10]

# Retain list elements value items
# Using dictionary comprehension
res = {key : val for key, val in test_dict.items() if val in tar_list}

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'gfg': 3, 'is': 2, 'best': 4, 'for': 7, 'geeks': 10}
The filtered dictionary : {'gfg': 3, 'best': 4, 'geeks': 10}

```

**方法 2:使用`filter()`+λ**
以上功能的组合可以解决这个问题。在这种情况下，我们使用过滤器执行过滤任务，使用 lambda 函数进行逻辑馈送。

```
# Python3 code to demonstrate working of 
# Retain list elements value items
# Using filter() + lambda

# initializing dictionary
test_dict = {'gfg': 3, 'is': 2, 'best': 4, 'for': 7, 'geeks': 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing target list 
tar_list = [3, 4, 10]

# Retain list elements value items
# Using filter() + lambda
res = dict(filter(lambda sub: sub[1] in tar_list, test_dict.items()))

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'gfg': 3, 'is': 2, 'best': 4, 'for': 7, 'geeks': 10}
The filtered dictionary : {'gfg': 3, 'best': 4, 'geeks': 10}

```