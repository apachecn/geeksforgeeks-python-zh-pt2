# Python–按列表排序元组

> 原文:[https://www.geeksforgeeks.org/python-order-tuples-by-list/](https://www.geeksforgeeks.org/python-order-tuples-by-list/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即需要使用外部列表对所有元组键进行排序。这个问题可以应用于数据科学等数据领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [('Gfg '，10)、(' best '，3)、(' CS '，8)、(' Geeks '，7)]、order _ list =[' Geeks '，' best '，' CS '，' Gfg']
> **输出** : [('Geeks '，7)、(' best '，3)、(' CS '，8)、(' Gfg '，10)]
> 
> **输入** : test_list = [('best '，3)、(' CS '，8)、(' Geeks '，7)]、order _ list =[' Geeks '，' best '，' CS']
> **输出** : [('Geeks '，7)、(' best '，3)、(' CS '，8)]

**方法一:使用`dict()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们通过将元组列表转换为字典来执行这个任务，作为第二步，使用列表理解来遍历列表，并将字典键与值进行映射。

```
# Python3 code to demonstrate working of 
# Order Tuples by List
# Using dict() + list comprehension

# initializing list
test_list = [('Gfg', 3), ('best', 9), ('CS', 10), ('Geeks', 2)]

# printing original list
print("The original list is : " + str(test_list))

# initializing order list 
ord_list = ['Geeks', 'best', 'CS', 'Gfg']

# Order Tuples by List
# Using dict() + list comprehension
temp = dict(test_list)
res = [(key, temp[key]) for key in ord_list]

# printing result 
print("The ordered tuple list : " + str(res)) 
```

**Output :**

```
The original list is : [('Gfg', 3), ('best', 9), ('CS', 10), ('Geeks', 2)]
The ordered tuple list : [('Geeks', 2), ('best', 9), ('CS', 10), ('Gfg', 3)]

```

**方法 2:使用`setdefault() + sorted()` +λ**
以上功能的组合可以解决这个问题。在本文中，我们执行将元素映射到索引并使用 setdefault 创建查找的任务。第二步，使用 sorted 使用查找字典值列表对列表进行排序。

```
# Python3 code to demonstrate working of 
# Order Tuples by List
# Using setdefault() + sorted() + lambda

# initializing list
test_list = [('Gfg', 3), ('best', 9), ('CS', 10), ('Geeks', 2)]

# printing original list
print("The original list is : " + str(test_list))

# initializing order list 
ord_list = ['Geeks', 'best', 'CS', 'Gfg']

# Order Tuples by List
# Using setdefault() + sorted() + lambda
temp = dict()
for key, ele in enumerate(ord_list):
    temp.setdefault(ele, []).append(key)       
res = sorted(test_list, key = lambda ele: temp[ele[0]].pop())  

# printing result 
print("The ordered tuple list : " + str(res)) 
```

**Output :**

```
The original list is : [('Gfg', 3), ('best', 9), ('CS', 10), ('Geeks', 2)]
The ordered tuple list : [('Geeks', 2), ('best', 9), ('CS', 10), ('Gfg', 3)]

```