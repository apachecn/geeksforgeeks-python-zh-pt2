# 计算双向元组对的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到计数-双向元组对/](https://www.geeksforgeeks.org/python-program-to-count-bidirectional-tuple-pairs/)

给定元组列表，计算双向元组。

> **输入** : test_list = [(5，6)，(1，2)，(6，5)，(9，1)，(6，5)，(2，1)]
> **输出** : 3
> **解释** : (1，2)，(2，1)；(5，6) - > [(6，5)，(6，5)]，共 3 对。
> 
> **输入** : test_list = [(5，6)，(1，3)，(6，5)，(9，1)，(6，5)，(2，1)]
> **输出** : 2
> **解释** : (5，6) - > [(6，5)，(6，5)]，共 2 对。

**方法:使用循环**

在这种情况下，我们检查每个元素是否有任何其他双向元素，一旦找到对，计数器就会递增。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Count Bidirectional Tuple Pairs
# Using loop

# initializing list
test_list = [(5, 6), (1, 2), (6, 5), (9, 1), (6, 5), (2, 1)]

# printing original list
print("The original list is : " + str(test_list))

res = 0
for idx in range(0, len(test_list)):
    for iidx in range(idx + 1, len(test_list)):

        # checking bidirection
        if test_list[iidx][0] == test_list[idx][1] and test_list[idx][1] == test_list[iidx][0]:
            res += 1

# printing result
print("Bidirectional pairs count : " + str(res))
```

**输出:**

> 原列表为:[(5，6)，(1，2)，(6，5)，(9，1)，(6，5)，(2，1)]
> 双向对计数:3