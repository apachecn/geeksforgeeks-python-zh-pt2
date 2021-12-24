# Python |每 N 个值后拆分 K 个元素

> 原文:[https://www . geesforgeks . org/python-split-k-elements-after-after-n-values/](https://www.geeksforgeeks.org/python-split-k-elements-after-every-n-values/)

简单的列表切片有许多应用，同时也存在许多列表分割的变体，可以来找我们解决。一个这样的问题可能是在每 N 个值之后拆分 K 个元素。让我们讨论解决这个特殊问题的方法。

**方法#1:使用循环**
这是解决这个特殊问题的幼稚而蛮力的方法借助循环，我们可以形成一个新的列表来检查每 N 个元素之后元素的 K 次出现。

```
# Python3 code to demonstrate
# Getting K elements after N values
# using loops

# initializing list
test_list = [4, 5, 2, 7, 8, 4, 10, 9, 11, 13]

# printing original list
print("The original list : " + str(test_list))

# initializing N and K
N = 2
K = 3

# using loops
# Getting K elements after N values
res =[]
while test_list:
    res += test_list[:K]
    test_list = test_list[K + N:]

# print result
print("The list after selective slicing : " + str(res))
```

**Output :**

```
The original list : [4, 5, 2, 7, 8, 4, 10, 9, 11, 13]
The list after selective slicing : [4, 5, 2, 4, 10, 9]

```