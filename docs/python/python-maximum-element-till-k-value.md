# Python–最大元素直到 K 值

> 原文:[https://www . geesforgeks . org/python-maximum-element-till-k-value/](https://www.geeksforgeeks.org/python-maximum-element-till-k-value/)

其中一个问题基本上是许多复杂问题的子问题，在 python 中找到列表中的最大数字直到某个数字，这是经常遇到的，本文讨论了这个特定问题的可能解决方案。

**方法#1:天真的方法**
解决这个问题最常见的方法是使用一个循环，并且最大化元素的出现次数，直到给定数量 k

```
# Python 3 code to demonstrate 
# Maximum element till K value
# using naive method 

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using naive method 
# Maximum element till K value
res = 0
for i in test_list :
    if i <= k :
        res = max(res, i)

# printing the intersection 
print ("The maximum number till K : " + str(res))
```

**Output :**

```
The list : [1, 7, 5, 6, 3, 8]
The maximum number till K : 3

```