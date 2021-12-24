# Python |嵌套列表测试

> 原文:[https://www.geeksforgeeks.org/python-test-for-nested-list/](https://www.geeksforgeeks.org/python-test-for-nested-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，我们需要发现列表是矩阵，或者列表包含列表作为其元素。这个问题可能出现在数据科学领域，因为它涉及矩阵的使用比以往更多。让我们讨论一下执行这项任务的具体方法。

**方法:使用`any() + isinstance()`**
以上功能的组合可以用来执行此任务。`any()`用于检查每个事件，`isinstance()`用于检查列表。

```
# Python3 code to demonstrate working of
# Test for nested list
# using any() + isinstance()

# initialize list
test_list = [[5, 6], 6, [7], 8, 10]

# printing original list
print("The original list is : " + str(test_list))

# Test for nested list
# using any() + isinstance()
res = any(isinstance(sub, list) for sub in test_list)

# printing result
print("Does list contain nested list ? : " + str(res))
```

**Output :**

```
The original list is : [[5, 6], 6, [7], 8, 10]
Does list contain nested list ? : True

```