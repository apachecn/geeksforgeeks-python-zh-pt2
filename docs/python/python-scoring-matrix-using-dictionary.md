# Python–使用字典的评分矩阵

> 原文:[https://www . geesforgeks . org/python-评分-矩阵-使用-字典/](https://www.geeksforgeeks.org/python-scoring-matrix-using-dictionary/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，需要解决 Python Matrix 记录中的评分问题。这意味着将字典的每个关键字及其值映射到每行的总得分。这种问题在游戏和网络开发领域也有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [['gfg '，' best']，['geeks']，['is '，' for ']
> **输出**:【18，15，12】
> 
> **输入** : test_list = [['gfg '，'极客'，' CS ']
> **输出** : [20]

**方法#1:使用循环**
这是可以执行该任务的方式之一。在这种情况下，我们迭代矩阵元素，使用字典执行值替换，并执行行求和。

```
# Python3 code to demonstrate working of 
# Scoring Matrix using Dictionary
# Using loop

# initializing list
test_list = [['gfg', 'is', 'best'], ['gfg', 'is', 'for', 'geeks']]

# printing original list
print("The original list is : " + str(test_list))

# initializing test dict
test_dict = {'gfg' : 5, 'is' : 10, 'best' : 13, 'for' : 2, 'geeks' : 15}

# Scoring Matrix using Dictionary
# Using loop
res = []
for sub in test_list:
    sum = 0
    for val in sub:
        if val in test_dict:
            sum += test_dict[val]
    res.append(sum)

# printing result 
print("The Row scores : " + str(res)) 
```

**Output :**

```
The original list is : [['gfg', 'is', 'best'], ['gfg', 'is', 'for', 'geeks']]
The Row scores : [28, 32]

```

**方法 2:使用列表理解+ `sum()`**
这是解决这个问题的又一种方法。在这种情况下，我们使用 sum()执行求和，列表理解用于迭代和分数分配。

```
# Python3 code to demonstrate working of 
# Scoring Matrix using Dictionary
# Using list comprehension + sum()

# initializing list
test_list = [['gfg', 'is', 'best'], ['gfg', 'is', 'for', 'geeks']]

# printing original list
print("The original list is : " + str(test_list))

# initializing test dict
test_dict = {'gfg' : 5, 'is' : 10, 'best' : 13, 'for' : 2, 'geeks' : 15}

# Scoring Matrix using Dictionary
# Using list comprehension + sum()
res = [sum(test_dict[word] if word.lower() in test_dict else 0 for word in sub) for sub in test_list]

# printing result 
print("The Row scores : " + str(res)) 
```

**Output :**

```
The original list is : [['gfg', 'is', 'best'], ['gfg', 'is', 'for', 'geeks']]
The Row scores : [28, 32]

```