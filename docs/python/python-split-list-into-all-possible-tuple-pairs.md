# Python–将列表拆分成所有可能的元组对

> 原文:[https://www . geesforgeks . org/python-split-list-in-all-to-all-可能的元组对/](https://www.geeksforgeeks.org/python-split-list-into-all-possible-tuple-pairs/)

给定一个列表，任务是编写一个 python 程序，可以将它拆分成所有可能的元组对组合。

> **输入:** test_list = [4，7，5，1，9]
> 
> **输出:** [[4，7，5，1，9]，[4，7，5，(1，9)]，[4，7，(5，1)，9]，[4，7，(5，9)，1]，[4，(7，5)，1，9]，[4，(7，5)，(1，9)]，[4，(7，1)，5，9]，[4，(7，1)，5，9]，[4，(7，1)，(5，9)]，[4，(7，9)，5，1]，[4，(7，9)，(5，1)] 7, (1, 9)], [(4, 5), (7, 1), 9], [(4, 5), (7, 9), 1], [(4, 1), 7, 5, 9], [(4, 1), 7, (5, 9)], [(4, 1), (7, 5), 9], [(4, 1), (7, 9), 5], [(4, 9), 7, 5, 1], [(4, 9), 7, (5, 1)], [(4, 9), (7, 5), 1], [(4, 9), (7, 1), 5]]
> 
> **说明:**形成所有对分区。
> 
> **输入:** test_list = [4，7，5，1]
> 
> **输出:** [[4，7，5，1]，[4，7，(5，1)]，[4，(7，5)，1]，[4，(7，1)，5]，[(4，7)，5，1]，[(4，7)，(5，1)]，[(4，5)，7，1]，[(4，5)，(7，1)]，[(4，1)，7，5]，[(4，1)，(7，5)]
> 
> **说明:**形成所有对分区。

**方法:**使用[切片](https://www.geeksforgeeks.org/string-slicing-in-python/)和[递归](https://www.geeksforgeeks.org/recursion-in-python/)

在这种情况下，我们从第一个元素开始执行所有的对创建，并使用递归通过适当的分区将多个元素转换成对。

## 蟒蛇 3

```py
def pairings(test_list):
    if len(test_list) <= 1:
        return [test_list]

    # keeping 1st element and attaching every element with it
    parts = [[test_list[0]] + ele for ele in pairings(test_list[1:])]
    for idx in range(1, len(test_list)):

        # pairing all possible from second element
        parts.extend([[(test_list[0], test_list[idx])] +
                      ele for ele in pairings(test_list[1: idx]
                                              + test_list[idx + 1:])])

    return parts

# initializing list
test_list = [4, 7, 5, 1]

# printing original list
print("The original list is : " + str(test_list))

# calling util. function
res = pairings(test_list)

# printing result
print("Created partitions : " + str(res))
```

**输出:**

> 原始列表是:[4，7，5，1]
> 
> 已创建分区:[[4，7，5，1]，[4，7，(5，1)]，[4，(7，5)，1]，[4，(7，1)，5]，[(4，7)，5，1]，[(4，7)，(5，1)]，[(4，5)，7，1]，[(4，5)，(7，1)]，[(4，1)，7，5]，[(4，1)，(7，5)]