# Python–从元组中移除嵌套记录

> 原文:[https://www . geesforgeks . org/python-remove-nested-records-from-tuple/](https://www.geeksforgeeks.org/python-remove-nested-records-from-tuple/)

有时，在处理记录时，我们可能会遇到这样的问题:记录的一个元素是另一个元组记录，我们可能不得不移除嵌套的记录。这是一个不常发生的问题，但是有一个解决方法是有用的。让我们讨论一下执行这项任务的具体方法。

**方法:使用 loop + `isintance() + enumerate()`**
使用上述功能可以解决这个问题。在这种情况下，我们只需使用`enumerate()`循环遍历元素以获取其索引计数，并使用`isinstance()`检查类型，然后通过检查忽略的元组记录来重新创建新的元组。

```py
# Python3 code to demonstrate working of
# Remove nested records
# using isinstance() + enumerate() + loop

# initialize tuple
test_tup = (1, 5, 7, (4, 6), 10)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Remove nested records
# using isinstance() + enumerate() + loop
res = tuple()
for count, ele in enumerate(test_tup):
    if not isinstance(ele, tuple):
        res = res + (ele, )

# printing result
print("Elements after removal of nested records : " + str(res))
```

**Output :**

```py
The original tuple : (1, 5, 7, (4, 6), 10)
Elements after removal of nested records : (1, 5, 7, 10)

```