# Python–具有最大记录元素的行

> 原文:[https://www . geesforgeks . org/python-带最大记录元素的行/](https://www.geeksforgeeks.org/python-row-with-maximum-record-element/)

有时，在使用 Python Records 时，我们可能会遇到一个问题，即我们需要找到具有最大记录元素的行。这种问题可能出现在 web 开发和日常编程领域。让我们讨论执行这项任务的某些方法。

> **输入**:test _ list =[(70，4)，(6，7)]，[(15，2)，(19，3)]
> **输出** : [(70，4)，(6，7)]
> 
> **输入**:test _ list =[(20，4)]，[(15，2)]，[(34，6)]
> **输出** : [(34，6)]

**方法一:使用 `max()` +键**
以上功能的组合可以解决这个问题。在这种情况下，我们使用 max()提取最大行，并使用 key 检查记录的初始元素。

```py
# Python3 code to demonstrate working of 
# Row with Maximum Record Element
# Using max() + key

# initializing list
test_list = [[(12, 4), (6, 7)], 
             [(15, 2), (19, 3)], 
             [(18, 3), (12, 4)], 
             [(17, 1), (11, 3)]]

# printing original list
print("The original list is : " + str(test_list))

# Row with Maximum Record Element
# Using max() + key
res = max(test_list, key = max)

# printing result 
print("The row with Maximum Value : " + str(res)) 
```

**Output :**

> 原列表为:[(12，4)，(6，7)]，[(15，2)，(19，3)]，[(18，3)，(12，4)]，[(17，1)，(11，3)]
> 最大值行:[(15，2)，(19，3)]

**方法 2:使用`max() + itemgetter()`**
这是解决这个问题的又一种方法。这种方法提供了在元素索引上进行选择以进行比较的灵活性，而不是像上面的方法那样通过 itemgetter()的使用来进行初始化。

```py
# Python3 code to demonstrate working of 
# Row with Maximum Record Element
# Using max() + itemgetter()
from operator import itemgetter

# initializing list
test_list = [[(12, 4), (6, 7)], 
             [(15, 2), (19, 3)], 
             [(18, 3), (12, 4)], 
             [(17, 1), (11, 3)]]

# printing original list
print("The original list is : " + str(test_list))

# Row with Maximum Record Element
# Using max() + itemgetter()
res = max(test_list, key = itemgetter(1))

# printing result 
print("The row with Maximum Value : " + str(res)) 
```

**Output :**

> 原列表为:[(12，4)，(6，7)]，[(15，2)，(19，3)]，[(18，3)，(12，4)]，[(17，1)，(11，3)]
> 最大值行:[(15，2)，(19，3)]