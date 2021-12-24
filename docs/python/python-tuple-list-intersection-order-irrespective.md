# Python–元组列表交集(顺序无关)

> 原文:[https://www . geesforgeks . org/python-元组-列表-交集-顺序-无关/](https://www.geeksforgeeks.org/python-tuple-list-intersection-order-irrespective/)

给定元组列表，执行元素的元组交集，而不考虑它们的顺序。

> **输入** : test_list1 = [(3，4)，(5，6)]，test_list2 = [(5，4)，(4，3)]
> **输出** : {(3，4)}
> **解释** : (3，4)和(4，3)是共同的，因此相交(顺序无关)。
> 
> **输入** : test_list1 = [(3，4)，(5，6)]，test_list2 = [(5，4)，(4，5)]
> **输出** : set()
> **解释**:不存在相交元素。

**方法#1:使用 sorted() + set() + &运算符+列表理解**
以上函数的组合可以用来解决这个问题。在这里，我们对元组进行排序，并使用&算子进行交集运算。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Tuple List intersection [ Order irrespective ]
# Using sorted() + set() + & operator + list comprehension

# initializing lists
test_list1 = [(3, 4), (5, 6), (9, 10), (4, 5)]
test_list2 = [(5, 4), (3, 4), (6, 5), (9, 11)]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Using sorted() + set() + & operator + list comprehension
# Using & operator to intersect, sorting before performing intersection
res = set([tuple(sorted(ele)) for ele in test_list1]) & set([tuple(sorted(ele)) for ele in test_list2])

# printing result
print("List after intersection : " + str(res))
```

**Output : **

```
The original list 1 is : [(3, 4), (5, 6), (9, 10), (4, 5)]
The original list 2 is : [(5, 4), (3, 4), (6, 5), (9, 11)]
List after intersection : {(4, 5), (3, 4), (5, 6)}
```

**方法 2:使用列表理解+地图()+ frozenset() + &操作符**
以上功能的组合可以用来执行这个任务。在这种情况下，我们执行将 innercontainers 转换为 set 的任务，该任务对其进行排序，并执行交集。Frozenset 用作其 hashable，map()需要 hashable 数据类型作为参数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Tuple List intersection [ Order irrespective ]
# Using list comprehension + map() + frozenset() + & operator

# initializing lists
test_list1 = [(3, 4), (5, 6), (9, 10), (4, 5)]
test_list2 = [(5, 4), (3, 4), (6, 5), (9, 11)]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Using list comprehension + map() + frozenset() + & operator
# frozenset used as map() requires hashable container, which
# set is not, result in frozenset format
res = set(map(frozenset, test_list1)) & set(map(frozenset, test_list2))

# printing result
print("List after intersection : " + str(res))
```

**Output : **

```
The original list 1 is : [(3, 4), (5, 6), (9, 10), (4, 5)]
The original list 2 is : [(5, 4), (3, 4), (6, 5), (9, 11)]
List after intersection : {frozenset({4, 5}), frozenset({5, 6}), frozenset({3, 4})}
```