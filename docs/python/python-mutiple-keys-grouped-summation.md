# Python–多键分组求和

> 原文:[https://www . geesforgeks . org/python-multi-key-group-summary/](https://www.geeksforgeeks.org/python-mutiple-keys-grouped-summation/)

有时，在处理 Python 记录时，我们会遇到一个问题，即我们需要基于多个键相等性来执行元素分组，并且还需要对特定键的分组结果进行求和。这种问题可能发生在数据领域的应用中。让我们讨论一下执行这项任务的具体方法。

> **输入** :
> test_list = [(12，' M '，' Gfg ')，(23，' H '，' Gfg ')，(13，' M '，' Best')]
> grp_indx = [1，2][indexes to group]
> sum _ idx =[0][Index to sum]
> **输出** : [('M '，' Gfg '，12)、(' H '，' Gfg '，23)、(' M '，' Best '，13)]
> 
> **输入** :
> test_list = [(12，' M '，' Gfg ')，(23，' M '，' Gfg ')，(13，' M '，' Best')]
> grp_indx = [1，2][indexes to group]
> sum _ idx =[0][Index to sum]
> **输出** : [('M '，' Gfg '，35)、(' M '，' Best '，13)]

**方法:使用 loop + defaultdict() +列表理解**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用循环来执行分组，并且使用列表理解来执行关键字求和的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Multiple Keys Grouped Summation
# Using loop + defaultdict() + list comprehension
from collections import defaultdict

# initializing list
test_list = [(12, 'M', 'Gfg'), (23, 'H', 'Gfg'),
            (13, 'M', 'Best'), (18, 'M', 'Gfg'),
            (2, 'H', 'Gfg'), (23, 'M', 'Best')]

# printing original list
print("The original list is : " + str(test_list))

# initializing grouping indices
grp_indx = [1, 2]

# initializing sum index
sum_idx = [0]

# Multiple Keys Grouped Summation
# Using loop + defaultdict() + list comprehension
temp = defaultdict(int)
for sub in test_list:
    temp[(sub[grp_indx[0]], sub[grp_indx[1]])] += sub[sum_idx[0]]
res = [key + (val, ) for key, val in temp.items()]

# printing result
print("The grouped summation : " + str(res))
```

**Output : **The original list is : [(12, ‘M’, ‘Gfg’), (23, ‘H’, ‘Gfg’), (13, ‘M’, ‘Best’), (18, ‘M’, ‘Gfg’), (2, ‘H’, ‘Gfg’), (23, ‘M’, ‘Best’)] The grouped summation : [(‘M’, ‘Gfg’, 30), (‘H’, ‘Gfg’, 25), (‘M’, ‘Best’, 36)]