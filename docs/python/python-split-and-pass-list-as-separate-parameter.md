# Python |分割和通过列表作为单独的参数

> 原文:[https://www . geesforgeks . org/python-拆分并传递列表作为单独参数/](https://www.geeksforgeeks.org/python-split-and-pass-list-as-separate-parameter/)

随着编程范例的出现，人们需要修改编码方式。其中一个范例就是 OOPS。在这种情况下，我们有一种称为模块化的技术，它代表制作不同的模块/功能，在程序中执行独立的任务。在这种情况下，我们需要传递的不仅仅是变量，还有一个列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用`tuple()`**
这个任务可以使用`tuple()`执行。在这种情况下，我们将对列表转换为元组，并通过这种方式将单个元素分离为变量，准备发送给函数。

```
# Python3 code to demonstrate working of
# Split and Pass list as separate parameter
# using tuple()

# Helper function for demonstration
def pass_args(arg1, arg2):
    print("The first argument is : " +  str(arg1))
    print("The second argument is : " +  str(arg2))

# initialize list
test_list = [4, 5]

# printing original list
print("The original list is : " + str(test_list))

# Split and Pass list as separate parameter
# using tuple()
one, two = tuple(test_list)
pass_args(one, two)
```

**Output :**

```
The original list is : [4, 5]
The first argument is : 4
The second argument is : 5

```