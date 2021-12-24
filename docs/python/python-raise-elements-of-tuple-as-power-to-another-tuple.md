# Python–将元组的元素作为另一个元组的动力

> 原文:[https://www . geeksforgeeks . org/python-将元组元素提升为另一个元组的幂/](https://www.geeksforgeeks.org/python-raise-elements-of-tuple-as-power-to-another-tuple/)

有时，在处理记录时，我们可能会遇到需要执行指数运算的问题，即元组的幂。这个问题可能发生在日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +生成器表达式**
以上功能的组合可用于执行该任务。在本例中，我们使用生成器表达式执行 power 任务，每个元组的映射索引由 zip()完成。

```
# Python3 code to demonstrate working of 
# Tuple exponentiation
# using zip() + generator expression 

# initialize tuples 
test_tup1 = (10, 4, 5, 6) 
test_tup2 = (5, 6, 7, 5) 

# printing original tuples 
print("The original tuple 1 : " + str(test_tup1)) 
print("The original tuple 2 : " + str(test_tup2)) 

# Tuple exponentiation 
# using zip() + generator expression 
res = tuple(ele1 ** ele2 for ele1, ele2 in zip(test_tup1, test_tup2)) 

# printing result 
print("The exponentiated tuple : " + str(res)) 
```

**Output :**

```
The original tuple 1 : (10, 4, 5, 6)
The original tuple 2 : (5, 6, 7, 5)
The exponentiated tuple : (100000, 4096, 78125, 7776)

```