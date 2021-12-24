# Python–第 n 个最小的大于 K

> 原文:[https://www . geesforgeks . org/python-n th-minist-大于-k/](https://www.geeksforgeeks.org/python-nth-smallest-greater-than-k/)

本文提供了各种方法来解决在 python 列表中找到大于 python 列表中特定元素 K 的第 n 个最小数字的问题。这基本上提供了从简单到单行的所有方法，以便在需要时可以在编程中使用。

**方法 1:天真方法+ `sort()`**
使用循环，我们继续添加大于 K 的元素，然后对列表进行排序，找到大于 K 的第 n 个元素

```
# Python 3 code to demonstrate 
# Nth smallest Greater than K
# using naive method + sort()

# Initializing list 
test_list = [1, 4, 7, 5, 10]

# Initializing k
k = 6

# Initializing N 
N = 2

# Printing original list 
print ("The original list is : " + str(test_list))

# Using naive method + sort()
# Nth smallest Greater than K
res = []
for i in test_list :
    if i > k :
        res.append(i)
res.sort()

# Printing result 
print ("The Nth minimum value greater than 6 is : " + str(res[N - 1]))
```

**Output :**

```
The original list is : [1, 4, 7, 5, 10]
The Kth minimum value greater than 6 is : 10

```