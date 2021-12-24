# Python–在嵌套元组中拆分

> 原文:[https://www . geesforgeks . org/python-嵌套式拆分元组/](https://www.geeksforgeeks.org/python-split-in-nested-tuples/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即需要通过某个分隔符对嵌套元组中的元素进行拆分。这种问题可以应用于不同的数据领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(3，(' Gfg '，' best '，6))，(10，(' CS '，' good '，9))]
> **输出** : [[3，' Gfg '，' best '，6]，[10，' CS '，' good '，9]]
> 
> **输入** : test_list = [(3，(1，2，3，6))]
> **输出** : [[3，1，2，3，6]]

**方法#1:使用列表理解+ `unpack operator(*)`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用*运算符和列表理解来执行通过分隔符来解包元素的任务，以进行迭代并形成对。

```py
# Python3 code to demonstrate working of 
# Split in Nested tuples
# Using list comprehension + unpack operator

# initializing list
test_list = [(3, ('Gfg', 'best')), (10, ('CS', 'good')), (7, ('Gfg', 'better'))]

# printing original list
print("The original list is : " + str(test_list))

# Split in Nested tuples
# Using list comprehension + unpack operator
res = [[a, *b] for a, b in test_list]

# printing result 
print("The splitted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [(3, ('Gfg', 'best')), (10, ('CS', 'good')), (7, ('Gfg', 'better'))]
The splitted elements : [[3, 'Gfg', 'best'], [10, 'CS', 'good'], [7, 'Gfg', 'better']]

```

**方法 2:使用`map() + list()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 map()执行将逻辑扩展到每个元素的任务，使用 list()将字符串打包到不同的容器中。

```py
# Python3 code to demonstrate working of 
# Split in Nested tuples
# map() + list()

# initializing list
test_list = [(3, ('Gfg', 'best')), (10, ('CS', 'good')), (7, ('Gfg', 'better'))]

# printing original list
print("The original list is : " + str(test_list))

# Split in Nested tuples
# map() + list()
res = []
for sub in test_list:
    res.append(list(map(str, (*[sub[0]], *[*sub[1]]))))

# printing result 
print("The splitted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [(3, ('Gfg', 'best')), (10, ('CS', 'good')), (7, ('Gfg', 'better'))]
The splitted elements : [[3, 'Gfg', 'best'], [10, 'CS', 'good'], [7, 'Gfg', 'better']]

```