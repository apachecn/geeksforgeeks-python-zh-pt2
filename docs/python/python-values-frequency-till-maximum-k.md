# Python |值频率直到最大值

> 原文:[https://www . geesforgeks . org/python-values-frequency-til-maximum-k/](https://www.geeksforgeeks.org/python-values-frequency-till-maximum-k/)

其中一个问题基本上是许多复杂问题的子问题，即在 python 的列表中查找小于某个数字的数字，这是经常遇到的问题，本文将讨论这个特定问题的可能解决方案。

**方法 1:天真方法**
解决这个问题最常见的方法是使用循环，只计算小于给定数字 k 的元素的出现次数

```
# Python 3 code to demonstrate 
# Values Frequency till Maximum K
# using naive method 

# initializing list
test_list = [1, 7, 5, 6, 3, 8]

# initializing k
k = 4

# printing list 
print ("The list : " + str(test_list))

# using naive method 
# to get numbers < k
count = 0
for i in test_list :
    if i < k :
        count = count + 1

# printing the result
print ("The numbers smaller than 4 : " + str(count))
```

**Output :**

```
The list : [1, 7, 5, 6, 3, 8]
The numbers smaller than 4 : 2

```