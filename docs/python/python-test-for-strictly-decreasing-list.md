# Python–严格递减列表测试

> 原文:[https://www . geesforgeks . org/python-严格递减列表测试/](https://www.geeksforgeeks.org/python-test-for-strictly-decreasing-list/)

单调序列的检验是一种效用，在数学中有多种应用，因此与数学相关的每个领域都有应用。由于数学和计算机科学通常是并行的，诸如检查严格递减序列的数学运算对于收集知识是有用的。让我们讨论执行该测试的某些方法。

**方法#1:使用`all() + zip()`**
all()通常会检查输入到它的所有元素。zip()的任务是从头开始链接列表，从第一个元素开始链接列表，这样就可以对所有元素执行检查。

```py
# Python 3 code to demonstrate 
# Test for strictly decreasing list
# using zip() + all()

# initializing list
test_list = [10, 8, 7, 5, 4, 1]

# printing original lists
print ("Original list : " + str(test_list))

# using zip() + all()
# Test for strictly decreasing list
res = all(i > j for i, j in zip(test_list, test_list[1:]))

# printing result
print ("Is list strictly decreasing ? : " + str(res))
```

**Output :**

```py
Original list : [10, 8, 7, 5, 4, 1]
Is list strictly decreasing ? : True

```