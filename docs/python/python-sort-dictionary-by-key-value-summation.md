# Python–按键值总和排序字典

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-key-value-summary/](https://www.geeksforgeeks.org/python-sort-dictionary-by-key-value-summation/)

给定一个字典，按键和值的总和排序。

> **输入** : test_dict = {3:5，1:3，4:6，2: 7，8:1}
> **输出** : {1: 3，3:5，2:7，8:1，4: 6}
> **解释** : 4 < 8 < 9 = 9 < 10 正在增加键和值的总和。
> 
> **输入** : test_dict = {3:5，1:3，4:6，2:7}
> **输出** : {1: 3，3:5，2:7，4: 6}
> **解释** : 4 < 8 < 9 < 10 正在增加键和值的总和。

**方法:使用排序的()+ lambda +项()**

在该排序操作中，使用 *sorted()，λ*函数用于提供加法逻辑。*项目()*用于获取键和值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Dictionary by key-value Summation
# Using sorted() + lambda + items()

# initializing dictionary
test_dict = {3: 5, 1: 3, 4: 6, 2: 7, 8: 1}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sorted() to sort, lambda provides key-value addition
res = sorted(test_dict.items(), key=lambda sub: sub[0] + sub[1])

# converting to dictionary
res = {sub[0]: sub[1] for sub in res}

# printing result
print("The sorted result : " + str(res))
```

**输出:**

```py
The original dictionary is : {3: 5, 1: 3, 4: 6, 2: 7, 8: 1}
The sorted result : {1: 3, 3: 5, 2: 7, 8: 1, 4: 6}
```