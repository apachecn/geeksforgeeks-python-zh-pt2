# Python |列表中第 I 个索引大小的子组

> 原文:[https://www . geesforgeks . org/python-子组列表中的索引大小/](https://www.geeksforgeeks.org/python-subgroups-of-ith-index-size-in-list/)

有时我们需要对元素进行分组，分组的技术和要求也相应地有所不同。对元素进行分组的一种方法是通过列表中的第 I 个大小，该列表存储索引键的字典，其值作为后续大小为 I 的列表元素。

> 输入:[4，7，8，10，12，15，13，17，14，5]
> 输出:{1: [4]，2: [7，8]，3: [10，12，15]，4: [13，17，14，5]}

让我们讨论一下实现这一点的某些方法。

**方法#1:使用`islice()` +字典理解**
切片方法可用于将需要制作的列表块分组为字典的值，然后使用字典理解将其分配给它们的指定索引键。

```py
# Python3 code to demonstrate
# Subgrouping of i'th index size in list
# using islice() + dictionary comprehension
from itertools import islice

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14, 5]

# printing original list 
print("The original list : " + str(test_list))

# using islice() + dictionary comprehension
# Subgrouping of i'th index size in list
temp = iter(test_list)
res = {key: val for key, val in ((i, list(islice(temp, i)))
                for i in range(1, len(test_list))) if val}

# printing result
print("The grouped dictionary is : " + str(res))
```

**Output :**

> 原始列表:[4，7，8，10，12，15，13，17，14，5]
> 分组字典为:{1: [4]，2: [7，8]，3: [10，12，15]，4: [13，17，14，5]}

**方法 2:使用`itemgetter() + takewhile() + islice()`**
为了提高计算速度，我们引入了新的函数来执行这个特定的任务，takewhile 和 itemgetter 函数执行对分片值进行分组的任务。

```py
# Python3 code to demonstrate
# Subgrouping of i'th index size in list
# using itemgetter() + takewhile() + islice()
from itertools import islice, takewhile
from operator import itemgetter

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14, 5]

# printing original list 
print("The original list : " + str(test_list))

# using itemgetter() + takewhile() + islice()
# Subgrouping of i'th index size in list
temp = iter(test_list)
res =  {key: val for key, val in 
        takewhile(itemgetter(1), ((i, list(islice(temp, i)))
        for i in range(1, len(test_list))))}

# printing result
print("The grouped dictionary is : " + str(res))
```

**Output :**

> 原始列表:[4，7，8，10，12，15，13，17，14，5]
> 分组字典为:{1: [4]，2: [7，8]，3: [10，12，15]，4: [13，17，14，5]}