# Python |真实记录

> 原文:[https://www.geeksforgeeks.org/python-true-record/](https://www.geeksforgeeks.org/python-true-record/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们有一条记录，我们需要检查它是否包含所有有效值。这种问题在数据预处理步骤中很常见。让我们讨论执行这项任务的某些方法。

**方法一:使用`not + any() + map()` + lambda**
组合上述功能可执行此任务。在这里，我们使用`any()`检查任何元素，逻辑的扩展由`map()`和λ完成。

```
# Python3 code to demonstrate working of
# True Record
# using any() + map() + lambda + not

# initialize tuple
test_tup = (True, True, True, True)

# printing original tuple
print("The original tuple : " + str(test_tup))

# True Record
# using any() + map() + lambda + not 
res = not any(map(lambda ele: not ele, test_tup))

# printing result
print("Is Tuple True ? : " + str(res))
```

**Output :**

```
The original tuple : (True, True, True, True)
Is Tuple True ? : True

```