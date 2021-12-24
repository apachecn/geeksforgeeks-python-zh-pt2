# Python |测试列表中是否存在所有元素

> 原文:[https://www . geesforgeks . org/python-如果所有元素都在列表中测试/](https://www.geeksforgeeks.org/python-test-if-all-elements-are-present-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要检查特定的值列表，并希望确定目标列表是否包含所有给定的值。当需要某种类型的过滤时，这在 web 开发领域有它的应用。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解+ `all()`**
这个任务可以使用 all()的内置功能来执行。all()可以被馈送列表理解逻辑，以检查测试列表的元素是否存在于目标列表中，其余的由`all()`完成。

```py
# Python3 code to demonstrate working of
# Test if all elements are present in list
# Using list comprehension + all()

# initializing list
target_list = [6, 4, 8, 9, 10]

# initializing test list 
test_list = [4, 6, 9]

# printing lists
print("The target list : " + str(target_list))
print("The test list : " + str(test_list))

# Test if all elements are present in list
# Using list comprehension + all()
res = all(ele in target_list for ele in test_list)

# Printing result
print("Does every element of test_list is in target_list ? : " + str(res))
```

**Output :**

```py

The target list : [6, 4, 8, 9, 10]
The test list : [4, 6, 9]
Does every element of test_list is in target_list ? : True

```