# Python–使用 K 元素的最大乘积

> 原文:[https://www . geesforgeks . org/python-max-product-use-k-elements/](https://www.geeksforgeeks.org/python-maximum-product-using-k-elements/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要最大化某些数字。最大化可以有很多条件。例如，通过使用 K 个元素来最大化产品。让我们讨论一下实现这一点的某些方法。

**方法一:使用`max() + sort()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们执行排序，然后通过使用 max()使用最佳的初始或尾部元素提取最大值。

```
# Python3 code to demonstrate 
# Maximum product using K elements
# using max() + sort() + list comprehension

# Initializing list
test_list = [8, 5, 9, 11, 3, 7]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 3

# Maximum product using K elements
# using max() + sort() + list comprehension
test_list.sort()
res = max(test_list[0] * test_list[1] * test_list[-1], test_list[-1] * test_list[-2] * test_list[-3])

# printing result 
print ("Maximum product using K elements : " + str(res))
```

**Output :**

```
The original list is : [8, 5, 9, 11, 3, 7]
Maximum product using K elements : 792

```