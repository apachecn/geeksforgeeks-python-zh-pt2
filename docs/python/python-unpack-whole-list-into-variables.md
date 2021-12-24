# Python |将整个列表解包为变量

> 原文:[https://www . geesforgeks . org/python-unpack-整张列表-进入变量/](https://www.geeksforgeeks.org/python-unpack-whole-list-into-variables/)

有时，在处理列表时，我们可能希望将列表的每个元素转换或解包为所需的变量。这个问题可能发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`"=" operator`**
这个任务可以使用“=”操作符来执行。在这种情况下，我们只需要确保足够多的变量作为列表元素的计数，并将它们分配给列表，列表元素按照它们的分配顺序被分配给变量。

```
# Python3 code to demonstrate working of
# Unpack whole list into variables
# using "=" operator

# initialize list
test_list = [1, 3, 7, 4, 2]

# printing original list
print("The original list is : " + str(test_list))

# Unpack whole list into variables
# using "=" operator
one, two, three, four, five = test_list

# printing result
print("Variables as assigned are : " + str(one) + " "
                                     + str(two) + " "
                                     + str(three) + " "
                                     + str(four) + " "
                                     + str(five))
```

**Output :**

```
The original list is : [1, 3, 7, 4, 2]
Variables as assigned are : 1 3 7 4 2

```