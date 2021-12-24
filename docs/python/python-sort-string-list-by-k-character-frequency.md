# Python–按 K 字符频率对字符串列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-string-list-by-k-character-frequency/](https://www.geeksforgeeks.org/python-sort-string-list-by-k-character-frequency/)

给定字符串列表，根据特定字符的频率执行排序操作。

> **输入**:test _ list =[“geekforgeckss”、“is”、“bessst”、“for”、“geeks”]，K = 's'
> **输出**:[‘bessst’，‘geekforgeckss’，‘geeks’，‘is’，‘for’]
> **解释** : bessst 有 3 个发生，geekforgeckss 有 3 个，以此类推。
> **输入**:test _ list =[“geek forgek ss”、“is”、“bessst”]，K = 'e'
> **输出**:[“geek forgek ss”、“bessst”、“is”]
> **解释**:按' e '计数的降序排列。

**方法#1:使用排序的()+计数()+λ**

在这种情况下，sorted()用于执行排序任务，count()用作执行排序的函数。使用额外的键参数，使用的函数封装是 lambda。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort String list by K character frequency
# Using sorted() + count() + lambda

# initializing list
test_list = ["geekforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 'e'

# "-" sign used to reverse sort
res = sorted(test_list, key = lambda ele: -ele.count(K))

# printing results
print("Sorted String : " + str(res))
```

**Output**

```py
The original list is : ['geekforgeeks', 'is', 'best', 'for', 'geeks']
Sorted String : ['geekforgeeks', 'geeks', 'best', 'is', 'for']
```

**方法 2:使用 sort() + count() + lambda**

在这种情况下，我们使用 sort()执行排序任务，这与上面类似，唯一的区别是排序是在一个地方完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort String list by K character frequency
# Using sort() + count() + lambda

# initializing list
test_list = ["geekforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 'e'

# "-" sign used to reverse sort
# inplace sort
test_list.sort(key = lambda ele: -ele.count(K))

# printing results
print("Sorted String : " + str(test_list))
```

**Output**

```py
The original list is : ['geekforgeeks', 'is', 'best', 'for', 'geeks']
Sorted String : ['geekforgeeks', 'geeks', 'best', 'is', 'for']
```