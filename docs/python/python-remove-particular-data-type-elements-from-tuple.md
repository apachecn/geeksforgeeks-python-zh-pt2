# Python–从元组中移除特定数据类型元素

> 原文:[https://www . geesforgeks . org/python-remove-special-data-type-elements-from-tuple/](https://www.geeksforgeeks.org/python-remove-particular-data-type-elements-from-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要从元组中移除特定的数据类型元素。这种问题可能发生在需要数据预处理的领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (4，5，' Gfg '，7.7，' Best ')，data_type = str
> **输出**:【4，5，7.7】
> 
> **输入** : test_tuple = (4，5，' Gfg '，7.7，' Best ')，data_type = float
> **输出** : [4，5，' Gfg '，' Best']

**方法#1:使用 loop + `isinstance()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们需要使用 isinstance()对每个元素进行迭代，如果元素与数据类型匹配，则丢弃该元素。

```py
# Python3 code to demonstrate working of 
# Remove particular data type Elements from Tuple
# Using loop + isinstance() 

# initializing tuple
test_tuple = (4, 5, 'Gfg', 7.7, 'Best')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing data type
data_type = int 

# Remove particular data type Elements from Tuple
# Using loop + isinstance()
res = []
for ele in test_tuple:
    if not isinstance(ele, data_type):
        res.append(ele)

# printing result 
print("The filtered tuple : " + str(res))
```

**Output :**

```py
The original tuple : (4, 5, 'Gfg', 7.7, 'Best')
The filtered tuple : ['Gfg', 7.7, 'Best']

```

**方法 2:使用列表理解+ `isinstance()`**
这是可以执行该任务的又一种方式。在这种情况下，我们需要通过列表理解使用速记来执行类似的任务。

```py
# Python3 code to demonstrate working of 
# Remove particular data type Elements from Tuple
# Using list comprehension + isinstance() 

# initializing tuple
test_tuple = (4, 5, 'Gfg', 7.7, 'Best')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing data type
data_type = int 

# Remove particular data type Elements from Tuple
# Using list comprehension + isinstance() 
res = [ele for ele in test_tuple if not isinstance(ele, data_type)]

# printing result 
print("The filtered tuple : " + str(res))
```

**Output :**

```py
The original tuple : (4, 5, 'Gfg', 7.7, 'Best')
The filtered tuple : ['Gfg', 7.7, 'Best']

```