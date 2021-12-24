# Python |测试元组是否不同

> 原文:[https://www . geesforgeks . org/python-test-if-tuple-is-distinct/](https://www.geeksforgeeks.org/python-test-if-tuple-is-distinct/)

有时，在处理记录时，我们会遇到一个问题，即我们需要找出元组的所有元素是否都不同。这在许多领域都有应用，包括网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的蛮力方式。在这种情况下，我们只需遍历所有元组元素，如果它是第一次出现，就将其放入集合中。在子序列发生期间，我们签入集合，如果它存在，我们返回 False。

```
# Python3 code to demonstrate working of
# Test if tuple is distinct
# Using loop

# initialize tuple 
test_tup = (1, 4, 5, 6, 1, 4)

# printing original tuple 
print("The original tuple is : " + str(test_tup))

# Test if tuple is distinct
# Using loop
res = True 
temp = set()
for ele in test_tup:
    if ele in temp:
        res = False 
        break
    temp.add(ele)

# printing result
print("Is tuple distinct ? : " + str(res))
```

**Output :**

```
The original tuple is : (1, 4, 5, 6, 1, 4)
Is tuple distinct ? : False

```