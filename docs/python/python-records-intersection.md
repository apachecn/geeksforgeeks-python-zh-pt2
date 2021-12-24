# Python |记录交集

> 原文:[https://www.geeksforgeeks.org/python-records-intersection/](https://www.geeksforgeeks.org/python-records-intersection/)

有时，在处理元组时，我们可能会遇到这样的问题，即我们需要两个记录的相似特征。这种类型的应用可以出现在数据科学领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`set() + "&" operator`**
该任务可以使用集合上异或运算符提供的对称差分功能来执行。到 set 的转换由 set()完成。

```
# Python3 code to demonstrate working of
# Records Intersection
# Using set() + "&" operator

# initialize tuples
test_tup1 = (3, 4, 5, 6)
test_tup2 = (5, 7, 4, 10)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Records Intersection
# Using set() + "&" operator
res = tuple(set(test_tup1) & set(test_tup2))

# printing result
print("The similar elements from tuples are : " + str(res))
```

**Output :**

```
The original tuple 1 : (3, 4, 5, 6)
The original tuple 2 : (5, 7, 4, 10)
The similar elements from tuples are : (4, 5)

```