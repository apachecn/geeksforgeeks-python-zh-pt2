# Python–测试元组是否包含 K

> 原文:[https://www . geesforgeks . org/python-test-if-tuple-contains-k/](https://www.geeksforgeeks.org/python-test-if-tuple-contains-k/)

有时候，在使用 Python 时，我们会遇到一个问题，我们有一个记录，我们需要检查它是否包含 k。这种问题在数据预处理步骤中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用 `any() + map()` + lambda**
组合上述功能可执行此任务。在本例中，我们使用 any()检查任何元素，逻辑的扩展由 map()和 lambda 完成。

```py
# Python3 code to demonstrate working of
# Test if Tuple contains K
# using any() + map() + lambda

# initialize tuple
test_tup = (10, 4, 5, 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize K 
K = 6

# Test if Tuple contains K
# using any() + map() + lambda
res = any(map(lambda ele: ele is K, test_tup))

# printing result
print("Does tuple contain any K value ? : " + str(res))
```

**Output :**

```py
The original tuple : (10, 4, 5, 6, 8)
Does tuple contain any K value ? : True

```