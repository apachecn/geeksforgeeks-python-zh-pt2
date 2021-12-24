# Python–测试列表中的所有元素是否属于同一类型

> 原文:[https://www . geesforgeks . org/python-如果列表中的所有元素都是同一类型，则进行测试/](https://www.geeksforgeeks.org/python-test-if-all-elements-in-list-are-of-same-type/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要测试参数的所有元素是否属于同一类型。这可以应用于许多领域，如数据科学和日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `isinstance()`**
上述功能的组合可用于执行该任务。在本例中，我们使用 isinstance()测试类型，并检查所有元素是否与第一个元素的类型相同。

```py
# Python3 code to demonstrate 
# Test if all elements in list are of same type
# using loop + isinstance()

# Initializing lists
test_list = [5, 6, 2, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# Test if all elements in list are of same type
# using loop + isinstance()
res = True
for ele in test_list:
    if not isinstance(ele, type(test_list[0])):
        res = False 
        break

# printing result 
print ("Do all elements have same type : " + str(res))
```

**Output :**

```py
The original list is : [5, 6, 2, 5, 7, 9]
Do all elements have same type : True

```