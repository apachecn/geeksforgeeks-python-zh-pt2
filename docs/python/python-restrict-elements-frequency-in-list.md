# Python–限制列表中的元素频率

> 原文:[https://www . geesforgeks . org/python-restrict-elements-frequency-in-list/](https://www.geeksforgeeks.org/python-restrict-elements-frequency-in-list/)

给定列表和元素频率列表，从频率列表中限制列表中元素的频率。

> **输入** : test_list = [1，4，5，4，1，4，5，5，6]，restrict _ dict = { 4:3，1 : 1，6 : 1，5 : 1}
> **输出**:【1，4，5，4，6】
> **解释**:1 的极限为 1，超过 1 的任何出现都会被移除。与所有元素相似。
> **输入** : test_list = [1，4，5，4，1，4，4，5，5，6]，restrict _ dict = { 4:2，1 : 1，6 : 1，5 : 1}
> **输出**:【1，4，5，4，6】
> **解释**:4 的极限为 3，超过这个极限的任何出现都会被移除。与所有元素相似。

**方法:使用 loop + defaultdict()**

在这种情况下，我们使用 defaultdict()迭代元素和并维护每个元素的查找计数器，如果任何元素超过 restrict dict，则该元素不会被添加。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Restrict Elements Frequency in List
# Using loop + defaultdict()
from collections import defaultdict

# initializing list
test_list = [1, 4, 5, 4, 1, 4, 4, 5, 5, 6]

# printing original list
print("The original list is : " + str(test_list))

# initializing restrct_dict
restrct_dict = {4 : 3, 1 : 1, 6 : 1, 5 : 2}

res = []
lookp = defaultdict(int)
for ele in test_list:
    lookp[ele] += 1

    # move to next ele if greater than restrct_dict count
    if lookp[ele] > restrct_dict[ele]:
        continue
    else:
        res.append(ele)

# printing results
print("Filtered List : " + str(res))
```

**Output**

```py
The original list is : [1, 4, 5, 4, 1, 4, 4, 5, 5, 6]
Filtered List : [1, 4, 5, 4, 4, 5, 6]
```