# Python–在元组中测试相似的数据类型

> 原文:[https://www . geesforgeks . org/python-test-相似-数据类型-in-tuple/](https://www.geeksforgeeks.org/python-test-similar-data-type-in-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要测试元组中的所有元素是否都具有相同的数据类型。这种问题可以应用于所有领域，如网络开发和日常编程。让我们讨论执行这项任务的某些方法。

```
Input : test_tuple = (5, 6, 7, 3, "Gfg")
Output : False

Input : test_tuple = (2, 3)
Output : True

```

**方法#1:使用 loop + `isinstance()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 isinstance()执行数据类型检查，迭代是以暴力的方式完成的，以说明所有的元素。

```
# Python3 code to demonstrate working of 
# Test Similar Data Type in Tuple
# Using isinstance() + loop

# initializing tuple
test_tuple = (5, 6, 7, 3, 5, 6)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Test Similar Data Type in Tuple
# Using isinstance() + loop
res = True
for ele in test_tuple:
    if not isinstance(ele, type(test_tuple[0])):
        res = False 
        break

# printing result 
print("Do all elements have same type ? : " + str(res))
```

**Output :**

```
The original tuple : (5, 6, 7, 3, 5, 6)
Do all elements have same type ? : True

```