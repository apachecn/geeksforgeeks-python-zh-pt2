# Python 程序求列表中每个 K 的组和

> 原文:[https://www . geeksforgeeks . org/python-program-to-find-the-group-sum-till-ever-k-in-a-list/](https://www.geeksforgeeks.org/python-program-to-find-the-group-sum-till-each-k-in-a-list/)

给定一个列表，任务是编写一个 Python 程序来执行求和分组，直到 K 出现。

**示例:**

> **输入** : test_list = [2，3，5，6，2，6，8，9，4，6，1]，K = 6
> **输出** : [10，6，2，6，21，6，1]
> **解释** : 2 + 3 + 5 = 10，6 之前分组累加。
> 
> **输入** : test_list = [2，3，5，6，2，6，8]，K = 6
> **输出** : [10，6，2，6，8]
> **解释** : 2 + 3 + 5 = 10，6 之前分组累计。

**方法:使用循环**

在这种情况下，我们维护一个求和计数器，如果 K 出现，求和将与 K 一起附加到结果列表中，否则求和计数器将使用当前值进行更新。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Group Sum till each K
# Using loop
from collections import defaultdict

# initializing list
test_list = [2, 3, 5, 6, 2, 6, 8, 9, 4, 6, 1]

# printing original lists
print("The original list is : " + str(test_list))

# initializing K
K = 6

temp_sum = 0
res = []
for ele in test_list:
    if ele != K:
        temp_sum += ele

    # append and re initializing if K occurs
    else:
        res.append(temp_sum)
        res.append(ele)
        temp_sum = 0

res.append(temp_sum)

# printing result
print("Computed list : " + str(res))
```

**Output**

```py
The original list is : [2, 3, 5, 6, 2, 6, 8, 9, 4, 6, 1]
Computed list : [10, 6, 2, 6, 21, 6, 1]
```