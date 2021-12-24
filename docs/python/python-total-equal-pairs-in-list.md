# Python–列表中的全部相等对

> 原文:[https://www . geesforgeks . org/python-total-equal-pairs-in-list/](https://www.geeksforgeeks.org/python-total-equal-pairs-in-list/)

给定一个列表，任务是编写一个 python 程序来计算总的相等数字对，即提取列表中所有可以与相似元素对偶的元素的个数。

```
Input : test_list = [2, 4, 5, 2, 5, 4, 2, 4, 5, 7, 7, 8, 3]
Output : 4

Explanation : 4, 2 and 5 have 3 occurrences, 7 has 2 occurrences, 1 pair each.

Input : test_list = [2, 4, 5, 2, 5, 4, 2, 4, 5, 7, 7, 8, 3, 3]
Output : 5

Explanation : 4, 2 and 5 have 3 occurrences, 1 pair each and 3, 7 have 2 occurrences, total 5 pairs.
```

**方法#1:使用** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/) **+** [**设置()**](https://www.geeksforgeeks.org/python-sets/)

在本例中，我们将容器转换为对原始列表中的每个元素设置并使用 *count()* 。将获得的商与 2 相加，得到所需的对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Total equal pairs in List
# Using loop + count()

# initializing lists
test_list = [2, 4, 5, 2, 5, 4, 2, 4, 5, 7, 7, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

all_ele = set(test_list)
res = 0
for ele in all_ele:

    # summing count from element list
    res += test_list.count(ele) // 2

# printing result
print("Total Pairs : " + str(res))
```

**输出:**

```
The original list is : [2, 4, 5, 2, 5, 4, 2, 4, 5, 7, 7, 8, 3]
Total Pairs : 4
```

**方法 2 :** [**使用 Counter()**](https://www.geeksforgeeks.org/counters-in-python-set-1/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/)

在这种情况下，获取每个元素的计数是使用 *Counter()* ， *sum()* 用于计算总对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Total equal pairs in List
# Using Counter() + list comprehension + sum()
from collections import Counter

# initializing lists
test_list = [2, 4, 5, 2, 5, 4, 2, 4, 5, 7, 7, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# using Counter for getting elements count
res = sum(ele // 2 for ele in Counter(test_list).values())

# printing result
print("Total Pairs : " + str(res))
```

**输出:**

```
The original list is : [2, 4, 5, 2, 5, 4, 2, 4, 5, 7, 7, 8, 3]
Total Pairs : 4
```